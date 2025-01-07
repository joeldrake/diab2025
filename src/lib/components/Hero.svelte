<section class="hero">
	<div class="hero-inner">
		<h1>Drake Innovation</h1>

		<div class="hero__headline">
			<h2>Joel<br />Drake</h2>
		</div>
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
		display: grid;
		background-image: url('/joeldrake.avif');
		background-size: cover;
		grid-template-columns: 1fr 1fr;
		width: 100%;
		max-width: var(--page-width);
		aspect-ratio: 1600 / 1067;
	}

	h1 {
		font-size: 1rem;
		margin: 0;
		z-index: 1;
		padding: 1rem var(--page-padding);
	}

	.hero__headline {
		z-index: 1;
		display: grid;
		justify-content: center;
		align-items: center;
	}

	h2 {
		font-size: 4.2rem;
		line-height: 1;

		font-family:
			Times,
			Times New Roman,
			Serif;
	}

	@media screen and (max-width: 980px) {
		h2 {
			font-size: 6.9vw;
		}
	}

	@media screen and (max-width: 400px) {
		h1 {
			font-size: 4vw;
			padding: 0.5rem 0 0.5rem 1rem;
		}
	}
</style>
