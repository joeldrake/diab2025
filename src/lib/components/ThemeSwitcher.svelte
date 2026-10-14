<script lang="ts">
	import { onMount } from 'svelte';

	type Preference = 'system' | 'light' | 'dark';

	const STORAGE_KEY = 'theme';
	const options: { value: Preference; label: string }[] = [
		{ value: 'system', label: 'System theme' },
		{ value: 'light', label: 'Light theme' },
		{ value: 'dark', label: 'Dark theme' }
	];

	// The inline script in app.html sets the real values before first paint;
	// this state only drives aria-checked once we're mounted.
	let preference = $state<Preference>('system');

	const systemQuery = () => window.matchMedia('(prefers-color-scheme: dark)');

	function readStored(): Preference {
		try {
			const stored = localStorage.getItem(STORAGE_KEY);
			if (stored === 'light' || stored === 'dark') return stored;
		} catch {
			// storage unavailable (private mode etc.) – fall back to system
		}
		return 'system';
	}

	function writeStored(value: Preference) {
		try {
			if (value === 'system') localStorage.removeItem(STORAGE_KEY);
			else localStorage.setItem(STORAGE_KEY, value);
		} catch {
			// ignore
		}
	}

	function resolve(value: Preference) {
		if (value === 'system') return systemQuery().matches ? 'dark' : 'light';
		return value;
	}

	function apply(value: Preference) {
		const root = document.documentElement;
		root.dataset.theme = resolve(value);
		root.dataset.themePreference = value;
	}

	function select(value: Preference) {
		if (value === preference) return;
		preference = value;
		writeStored(value);

		const reduceMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
		if (!document.startViewTransition || reduceMotion) {
			apply(value);
			return;
		}
		document.startViewTransition(() => apply(value));
	}

	function handleKeydown(event: KeyboardEvent) {
		const step = { ArrowRight: 1, ArrowDown: 1, ArrowLeft: -1, ArrowUp: -1 }[event.key];
		if (!step) return;
		event.preventDefault();
		const index = options.findIndex((o) => o.value === preference);
		const next = options[(index + step + options.length) % options.length];
		select(next.value);
		(event.currentTarget as HTMLElement)
			.querySelector<HTMLButtonElement>(`[data-value="${next.value}"]`)
			?.focus();
	}

	onMount(() => {
		preference = readStored();
		apply(preference);

		const query = systemQuery();
		const onSystemChange = () => {
			if (preference === 'system') apply('system');
		};
		query.addEventListener('change', onSystemChange);
		return () => query.removeEventListener('change', onSystemChange);
	});
</script>

<div
	class="theme-switcher"
	role="radiogroup"
	aria-label="Color theme"
	tabindex="-1"
	onkeydown={handleKeydown}
>
	<span class="theme-switcher__indicator" aria-hidden="true"></span>
	{#each options as option (option.value)}
		{@const checked = preference === option.value}
		<button
			type="button"
			role="radio"
			class="theme-switcher__option"
			data-value={option.value}
			aria-checked={checked}
			aria-label={option.label}
			title={option.label}
			tabindex={checked ? 0 : -1}
			onclick={() => select(option.value)}
		>
			<svg
				viewBox="0 0 24 24"
				fill="none"
				stroke="currentColor"
				stroke-width="2"
				stroke-linecap="round"
				stroke-linejoin="round"
				aria-hidden="true"
			>
				{#if option.value === 'system'}
					<rect x="2" y="3" width="20" height="14" rx="2" />
					<path d="M8 21h8M12 17v4" />
				{:else if option.value === 'light'}
					<circle cx="12" cy="12" r="4" />
					<path
						d="M12 2v2M12 20v2M4.93 4.93l1.41 1.41M17.66 17.66l1.41 1.41M2 12h2M20 12h2M6.34 17.66l-1.41 1.41M19.07 4.93l-1.41 1.41"
					/>
				{:else}
					<path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z" />
				{/if}
			</svg>
		</button>
	{/each}
</div>

<style>
	.theme-switcher {
		--size: 1.75rem;
		--gap: 2px;
		--index: 0;

		position: relative;
		display: inline-flex;
		gap: var(--gap);
		padding: var(--gap);
		border-radius: 999px;
		border: 1px solid color-mix(in srgb, var(--border) 70%, transparent);
		background: color-mix(in srgb, var(--color-background-secondary) 70%, transparent);
		backdrop-filter: blur(8px);
		-webkit-backdrop-filter: blur(8px);
		outline: none;
	}

	:global(html[data-theme-preference='light']) .theme-switcher {
		--index: 1;
	}

	:global(html[data-theme-preference='dark']) .theme-switcher {
		--index: 2;
	}

	.theme-switcher__indicator {
		position: absolute;
		top: var(--gap);
		left: var(--gap);
		width: var(--size);
		height: var(--size);
		border-radius: 999px;
		background: var(--color-background-primary);
		box-shadow:
			0 1px 2px rgb(0 0 0 / 0.12),
			0 0 0 1px color-mix(in srgb, var(--border) 60%, transparent);
		transform: translateX(calc(var(--index) * (var(--size) + var(--gap))));
		transition: transform 250ms cubic-bezier(0.3, 0.7, 0.3, 1);
		view-transition-name: theme-indicator;
	}

	.theme-switcher__option {
		position: relative;
		display: grid;
		place-items: center;
		width: var(--size);
		height: var(--size);
		padding: 0;
		border: none;
		border-radius: 999px;
		background: none;
		color: var(--color-text-subtle);
		cursor: pointer;
		transition: color 150ms ease;
	}

	.theme-switcher__option:hover,
	.theme-switcher__option[aria-checked='true'] {
		color: var(--color-text-primary);
	}

	.theme-switcher__option:focus-visible {
		outline: 2px solid var(--color-interactive-primary);
		outline-offset: 1px;
	}

	.theme-switcher__option svg {
		width: 1rem;
		height: 1rem;
	}

	@media screen and (max-width: 300px) {
		.theme-switcher {
			--size: 1.5rem;
		}

		.theme-switcher__option svg {
			width: 0.875rem;
			height: 0.875rem;
		}
	}

	@media (prefers-reduced-motion: reduce) {
		.theme-switcher__indicator,
		.theme-switcher__option {
			transition: none;
		}
	}

	::view-transition-group(*),
	::view-transition-old(*),
	::view-transition-new(*) {
		animation-duration: 300ms;
		animation-timing-function: cubic-bezier(0.3, 0.7, 0.3, 1);
	}
</style>
