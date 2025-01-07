<script lang="ts">
	import { browser } from '$app/environment';
	const html = browser ? document?.querySelector('html') : undefined;
	let theme = html?.getAttribute('data-theme');
	function handleDarkmodeClick() {
		const newTheme = theme === 'dark' ? 'light' : 'dark';

		document?.querySelector('html')?.setAttribute('data-theme', newTheme);

		localStorage.setItem('theme', newTheme);

		theme = newTheme;
	}
</script>

<section class="hero">
	<div class="hero-inner">
		<div class="hero__headline">
			<h1>Joel<br />Drake</h1>
		</div>
		<button
			class="hero__darkmode-toggle"
			onclick={handleDarkmodeClick}
			aria-label="Toggle Light/Dark Mode"
		>
			{#if theme === 'dark'}
				<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
					<path
						fill="currentColor"
						d="M10.999-.004h2.004V2h-2.004V-.004ZM4.223 2.803L5.64 4.22L4.223 5.637L2.806 4.22l1.417-1.417Zm15.556 0l1.417 1.417l-1.417 1.417l-1.417-1.417l1.417-1.417ZM12 6a6 6 0 1 0 0 12a6 6 0 0 0 0-12Zm-8 6a8 8 0 1 1 16 0a8 8 0 0 1-16 0Zm-4.001-1.004h2.004V13H-.001v-2.004Zm22 0h2.004V13h-2.004v-2.004ZM4.223 18.36l1.417 1.417l-1.417 1.418l-1.417-1.418l1.417-1.417Zm15.556 0l1.417 1.417l-1.417 1.417l-1.417-1.417l1.417-1.416ZM11 21.997h2.004V24H11v-2.004Z"
					/>
				</svg>
			{:else}
				<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
					<path
						fill="currentColor"
						d="m15.844 3.344l-1.428.781l1.428.781l.781 1.428l.781-1.428l1.428-.781l-1.428-.781l-.781-1.428l-.781 1.428Zm-5.432.814A8 8 0 1 0 18.93 16A9 9 0 0 1 10 7c0-.98.131-1.937.412-2.842ZM2 12C2 6.477 6.477 2 12 2h1.734l-.868 1.5C12.287 4.5 12 5.69 12 7a7 7 0 0 0 8.348 6.87l1.682-.327l-.543 1.626C20.162 19.137 16.417 22 12 22C6.477 22 2 17.523 2 12Zm18.5-5.584l.914 1.67l1.67.914l-1.67.914l-.914 1.67l-.914-1.67L17.916 9l1.67-.914l.914-1.67Z"
					/>
				</svg>
			{/if}
		</button>
	</div>
</section>

<style>
	.hero {
		display: flex;
		justify-content: center;
		padding: var(--page-padding);
	}

	.hero-inner {
		position: relative;
		background-image: url('/joeldrake.avif');
		background-size: cover;
		width: 100%;
		max-width: var(--page-width);
		aspect-ratio: 1600 / 1067;
	}

	.hero__darkmode-toggle {
		position: absolute;
		top: 0.75rem;
		right: 0.75rem;
		border: none;
		text-decoration: none;
		background: none;
		cursor: pointer;
		color: #222;
		padding: 0;
	}

	@media screen and (max-width: 300px) {
		.hero__darkmode-toggle {
			top: 0.5rem;
			right: 0.5rem;
		}
	}

	.hero__darkmode-toggle svg {
		width: min(24px, 6vw);
		height: auto;
	}

	.hero__headline {
		position: absolute;
		width: 50%;
		height: 100%;
		top: 0;
		right: 0;
		display: grid;
		justify-content: center;
		align-items: center;
	}

	h1 {
		font-size: min(5rem, 9vw);
		line-height: 1;
		color: #222;

		font-family:
			Times,
			Times New Roman,
			Serif;
	}
</style>
