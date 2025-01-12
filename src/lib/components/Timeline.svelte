<section class="timeline page-section">
	<div class="timeline-inner page-section-inner">
		<h2>Professional Timeline</h2>

		<div class="timeline-box">
			<h3>2025</h3>
			<p>
				Continuing consulting work with the same project and team from 2019. The project's scope and
				the team have grown over the years.
			</p>

			<h3>2019</h3>
			<p>Joined a team building a web app for a major retail company in Sweden.</p>

			<h3>2015</h3>
			<p>Launched a tech startup called Infoping together with ett.se.</p>

			<h3>2013</h3>
			<p>Studied Copywriting at Berghs School of Communication (evening course).</p>

			<h3>2012</h3>
			<p>Studied Graphic Design at Berghs School of Communication (evening course).</p>

			<h3>2011</h3>
			<p>Started a company called ett.se together with colleagues from OpenText.</p>

			<h3>2008</h3>
			<p>Started as tech support at OpenText.</p>
		</div>
	</div>
</section>

<style>
	.timeline {
		--border-width: 3px;
	}

	.timeline-box {
		position: relative;
		border-left: var(--border-width) solid var(--border);
		padding-left: 1.5rem;
		margin-left: var(--border-width);
	}

	.timeline-box:before {
		content: '';
		position: absolute;
		top: 0;
		left: -8px;
		width: 16px;
		height: 16px;
		background-color: var(--color-background-primary);
	}

	h3 {
		position: relative;
		margin-top: 2rem;
	}

	h3:first-child {
		margin-top: 0;
	}

	h3:before {
		content: '';
		position: absolute;
		top: 1rem;
		left: -1.98rem;
		width: 0.75rem;
		height: 0.75rem;
		border-radius: 100%;
		box-shadow: 0 0 0 6px var(--color-background-primary);
		background-color: var(--border);
	}

	@media screen and (max-width: 600px) {
		h3:before {
			top: 0.75rem;
		}
	}

	p {
		margin-top: 0;
	}
</style>
