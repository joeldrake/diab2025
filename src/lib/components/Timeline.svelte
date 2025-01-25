<section class="timeline page-section">
	<div class="timeline-inner page-section-inner">
		<h2>Professional Timeline</h2>

		<div class="timeline-box">
			<h3>2025</h3>
			<p>
				Feeling privileged to continue working on the same retail project. Good team, fun tech stack
				and interesting challenges.<br />
				<i>
					Skill level: Senior web developer. Programming skills starting to reach John Carmack
					levels.
				</i>
			</p>

			<h3>2019</h3>
			<p>
				Joined a team building a web app for a major retail company in Sweden.<br />
				<i>Skill upgrades: Vue, GraphQL, Typescript, Svelte.</i>
			</p>

			<h3>2015</h3>
			<p>
				Launched a tech startup called Infoping together with ett.se.<br />
				<i>
					Skill level: Philanthropic entrepreneur. Like Bill Gates but without the money. Started
					using React.
				</i>
			</p>

			<h3>2013</h3>
			<p>
				Studied Copywriting at Berghs School of Communication (evening course).<br />
				<i>Skill upgrades: Idea generation, Communication, Project briefs, Language, Rhetoric.</i>
			</p>

			<h3>2012</h3>
			<p>
				Studied Graphic Design at Berghs School of Communication (evening course).<br />
				<i>Skill upgrades: Web Design, Typography, Color, Layout.</i>
			</p>

			<h3>2011</h3>
			<p>
				Started a company called ett.se together with colleagues from OpenText.<br />
				<i>Skill level: Technical evangelist. Using PHP + jQuery.</i>
			</p>

			<h3>2008</h3>
			<p>
				Started as tech support at OpenText.<br />
				<i>Skill level: Rising tech star</i>
			</p>
		</div>
	</div>
</section>

<style>
	.timeline {
		--border-width: 3px;
	}

	i {
		color: var(--color-text-subtle);
		font-size: 0.9rem;
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
