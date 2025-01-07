<div class="CV">
	<h1 class="CV__title">CV</h1>
	<p class="CV__info">
		<strong>Joel Drake, 1985/05/20</strong>
		<br />
		Surbrunnsgatan 11, <span class="CV__address_under">114 27, Stockholm</span>
		<br />
		+46 (0) 70 692 32 25
		<br />
		joel@drakeinnovation.se
	</p>
	<img
		class="CV__image"
		src="/joel_squared_small.jpg"
		alt="Joel Drake"
		width="100px"
		height="100px"
	/>

	<h2 class="CV__title_under">Work in IT</h2>

	<p class="CV__item_time">2019 - ongoing</p>
	<p class="CV__item_text">
		<strong class="CV__item_text_headline">Web Consultant, RetailOnly</strong>

		Part of a team building a web app for ICA. Working tightly together with business analysts and
		UI/UX experts to construct the product.
	</p>

	<p class="CV__item_time">2015 - 2019</p>
	<p class="CV__item_text">
		<strong class="CV__item_text_headline">Co-founder & Web developer, Infoping</strong>

		Tech startup created with ett.se. I designed and built the front-end of the platform, which
		included a public website, an admin dashboard and a PWA.
	</p>

	<p class="CV__item_time">2011 - 2019</p>
	<p class="CV__item_text">
		<strong class="CV__item_text_headline">Co-founder, ett.se</strong>

		We were a team of five people that worked together between 2008 and 2019, with collaboration
		solutions and digital communication. In 2011 we launched ett.se and started to focus more on the
		development of our own products and services.
	</p>
	<p class="CV__item_time">2008 - 2011</p>
	<p class="CV__item_text">
		<strong class="CV__item_text_headline">Tech support, OpenText</strong>

		Technical Support for the email and collaboration system FirstClass, in Sweden and Scandinavia.
	</p>

	<h2 class="CV__title_under">Education</h2>

	<p class="CV__item_time">2013</p>
	<p class="CV__item_text">
		<strong class="CV__item_text_headline"
			>Copywriting, Berghs School of Communication (evening course)</strong
		>

		Creativity and idea generation, Commercial Communication, The roles of an advertising writer,
		Project briefs, Language, Rhetoric.
	</p>

	<p class="CV__item_time">2012</p>
	<p class="CV__item_text">
		<strong class="CV__item_text_headline"
			>Graphic design, Berghs School of Communication (evening course)</strong
		>

		Advertising, Photography, Print, Web Design, Illustration, Typography, Color, Layout.
	</p>

	<p class="CV__item_time">2005 - 2008</p>
	<p class="CV__item_text">
		<strong class="CV__item_text_headline"
			>Media and Communications Studies, Örebro University</strong
		>

		Film Theory, Film Aesthetics, Media Analysis, Mass Media, Communication Theory, Television
		Studies, Science Theory, English.
	</p>
	<p class="CV__item_time">2001 - 2004</p>
	<p class="CV__item_text">
		<strong class="CV__item_text_headline">Computer Science, Bruksgymnasiet Gimo</strong>

		Programming, Local Networking, Operating Systems, Web Design, Web Server, Graphic
		Communications, Multimedia, Psychology.
	</p>

	<p class="CV__footer">
		<i>References available upon request.</i>
	</p>
</div>

<style>
	.CV {
		padding: 3rem 2rem;

		max-width: 768px;
		margin: 0 auto;

		display: grid;
		grid-template-columns:
			[col-left] minmax(100px, auto) [col-center] 1fr [col-right] minmax(100px, auto)
			[col-end];
		gap: 1.5em;
		line-height: 1.2;
	}

	.CV__info {
		line-height: 1.3;
	}

	.CV p {
		padding: 0;
		margin: 0;
	}

	.CV__title,
	.CV__title_under {
		font-family: Times, 'Times New Roman', Serif;
	}

	.CV__title {
		margin-top: -0.1em;
		margin-bottom: 0;
		line-height: 1;
		font-size: 6.9em;
		letter-spacing: -2px;
	}

	.CV__image {
		width: 20vw;
		max-width: 100px;
		min-width: 100px;
		height: auto;
		grid-column-start: col-right;
		grid-column-end: col-end;

		grid-row-start: 0;
		grid-row-end: 1;
	}

	.CV__address_under {
		white-space: nowrap;
	}

	.CV__item_text_headline {
		display: block;
	}

	.CV__title_under {
		margin: 0;
		font-size: 2em;
		grid-column-start: col-left;
		grid-column-end: col-end;
		border-bottom: 2px solid var(--color-text-primary);
	}

	p.CV__footer {
		grid-column-start: col-left;
		grid-column-end: col-end;
		margin-top: 2em;
	}

	.CV__item_time {
		grid-column-start: col-left;
		grid-column-end: col-center;
	}

	.CV__item_text {
		grid-column-start: col-center;
		grid-column-end: col-right;
	}

	@media screen and (max-width: 768px) {
		.CV {
			gap: 1em;
		}
		.CV__title {
			grid-column-start: col-left;
			grid-column-end: col-end;
			text-align: center;
		}

		.CV__info {
			grid-column-start: col-left;
			grid-column-end: col-end;
			text-align: center;
		}

		.CV__image {
			grid-column-start: col-left;
			grid-column-end: col-end;

			grid-row-start: 2;
			grid-row-end: 3;
			margin: 0 auto;
		}

		.CV__item_text {
			grid-column-end: col-end;
		}
	}

	@media screen and (max-width: 500px) {
		.CV {
			padding: 2rem 1rem;
		}

		.CV__item_time {
			grid-column-start: col-left;
			grid-column-end: col-end;
		}

		p.CV__item_text {
			grid-column-start: col-left;
			margin-bottom: 2em;
		}
	}

	@media print {
		.CV {
			font-size: 14px;
			max-width: 100%;
		}

		@page {
			size: auto;
			margin: 16px;
		}
	}
</style>
