<script lang="ts">
	import ThemeSwitcher from './ThemeSwitcher.svelte';
</script>

<section class="hero page-section">
	<div class="hero-inner page-section-inner">
		<div class="hero__headline">
			<h1>Joel<br />Drake</h1>
		</div>
		<div class="hero__theme-switcher">
			<ThemeSwitcher />
		</div>
	</div>
</section>

<style>
	.hero {
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

	.hero__theme-switcher {
		position: absolute;
		top: 0.75rem;
		right: 0.75rem;
		z-index: 1;
	}

	@media screen and (max-width: 300px) {
		.hero__theme-switcher {
			top: 0.5rem;
			right: 0.5rem;
		}
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
		color: var(--gray-9);

		font-family:
			Times,
			Times New Roman,
			Serif;
	}
</style>
