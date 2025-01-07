<section class="timeline">
	<div class="timeline-inner">
		<h2>Professional Timeline</h2>

		<div class="timeline-box">
			<h3>2025</h3>
			<p>
				Continuing to work as a consultant, on the retail web app. The project's scope and the team
				have grown over the years. It’s a great employer, with a modern and rewarding tech stack,
				and fantastic colleagues.
			</p>

			<h3>2019</h3>
			<p>Joined a team building a web app for a major retail company in Sweden.</p>

			<h3>2015</h3>
			<p>
				Launched a tech startup called Infoping together with ett.se. Infoping is a communication
				service based on SMS and push notifications.
			</p>

			<h3>2013</h3>

			<p>Studied Copywriting at Berghs School of Communication (evening course).</p>

			<h3>2012</h3>
			<p>Studied Graphic Design at Berghs School of Communication (evening course).</p>

			<h3>2011</h3>
			<p>
				Started a company called ett.se together with colleagues from OpenText. Here, we were able
				to focus more on the development of our own products and services.
			</p>

			<h3>2008</h3>
			<p>
				Started as tech support at OpenText. The product I supported was an email and collaboration
				system.
			</p>
		</div>
	</div>
</section>

<style>
	.timeline {
		display: flex;
		justify-content: center;
		--border-width: 3px;
	}

	.timeline-inner {
		width: 100%;
		max-width: 768px;
		padding: var(--page-padding);
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
