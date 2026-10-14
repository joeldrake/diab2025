<script lang="ts">
	const year = new Date().getFullYear();
</script>

<footer class="footer page-section">
	<div class="footer-inner page-section-inner">
		<div class="footer__contact">
			<h2 id="contact">Get in touch</h2>
			<p class="footer__lead">
				Send me an email or a message on social media if you want to get in touch with me.
			</p>
			<a class="footer__mail" href="mailto:joel@drakeinnovation.se">joel@drakeinnovation.se</a>
		</div>

		<div class="footer__bottom">
			<p class="footer__legal">
				<span>© {year} Drake Innovation AB</span>
				<span class="footer__sep" aria-hidden="true">·</span>
				<span>Org. no. 559208-1227</span>
			</p>

			<ul class="footer__social" aria-label="Social media">
				<li>
					<a
						href="https://bsky.app/profile/joeldrake.bsky.social"
						aria-label="Joel Drake on Bluesky"
						title="Bluesky"
					>
						<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" aria-hidden="true">
							<path
								fill="currentcolor"
								d="M3.468 1.948C5.303 3.325 7.276 6.118 8 7.616c.725-1.498 2.697-4.29 4.532-5.668C13.855.955 16 .186 16 2.632c0 .489-.28 4.105-.444 4.692-.572 2.04-2.653 2.561-4.504 2.246 3.236.551 4.06 2.375 2.281 4.2-3.376 3.464-4.852-.87-5.23-1.98-.07-.204-.103-.3-.103-.218 0-.081-.033.014-.102.218-.379 1.11-1.855 5.444-5.231 1.98-1.778-1.825-.955-3.65 2.28-4.2-1.85.315-3.932-.205-4.503-2.246C.28 6.737 0 3.12 0 2.632 0 .186 2.145.955 3.468 1.948Z"
							/>
						</svg>
					</a>
				</li>
				<li>
					<a href="https://github.com/joeldrake" aria-label="Joel Drake on GitHub" title="GitHub">
						<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" aria-hidden="true">
							<path
								fill="currentcolor"
								d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"
							/>
						</svg>
					</a>
				</li>
			</ul>
		</div>
	</div>
</footer>

<style>
	.footer {
		--footer-fg: var(--color-background-primary);
		--footer-muted: color-mix(in srgb, var(--footer-fg) 65%, transparent);
		--footer-line: color-mix(in srgb, var(--footer-fg) 18%, transparent);

		background-color: var(--color-text-primary);
		color: var(--footer-fg);
		margin-top: var(--page-padding-large);
	}

	.footer-inner {
		padding-block: var(--page-padding-large) var(--page-padding);
	}

	h2 {
		margin: 0 0 0.75rem;
		letter-spacing: -0.02em;
	}

	.footer__lead {
		margin: 0 0 1.5rem;
		max-width: 32rem;
		color: var(--footer-muted);
		line-height: 1.6;
	}

	a {
		color: inherit;
		text-decoration: none;
	}

	.footer__mail {
		display: inline-block;
		font-size: clamp(1.125rem, 4vw, 1.5rem);
		font-weight: 600;
		text-decoration: underline;
		text-decoration-color: var(--footer-line);
		text-decoration-thickness: 2px;
		text-underline-offset: 0.3em;
		overflow-wrap: anywhere;
		transition: text-decoration-color 0.2s ease;
	}

	.footer__mail:hover {
		text-decoration-color: currentcolor;
	}

	.footer__bottom {
		display: flex;
		flex-wrap: wrap;
		align-items: center;
		justify-content: space-between;
		gap: 1rem;
		margin-top: var(--page-padding-large);
		padding-top: 1.5rem;
		border-top: 1px solid var(--footer-line);
	}

	.footer__legal {
		display: flex;
		flex-wrap: wrap;
		gap: 0 0.5rem;
		margin: 0;
		font-size: 0.875rem;
		color: var(--footer-muted);
	}

	.footer__social {
		display: flex;
		gap: 0.5rem;
		margin: 0;
		padding: 0;
		list-style: none;
	}

	.footer__social a {
		display: grid;
		place-items: center;
		width: 2.5rem;
		height: 2.5rem;
		border-radius: 50%;
		color: var(--footer-muted);
		transition:
			color 0.2s ease,
			background-color 0.2s ease;
	}

	.footer__social a:hover {
		color: var(--footer-fg);
		background-color: var(--footer-line);
	}

	.footer__social svg {
		width: 1.25rem;
		height: 1.25rem;
	}

	a:focus-visible {
		outline: 2px solid currentcolor;
		outline-offset: 3px;
	}

	@media screen and (max-width: 400px) {
		.footer__sep {
			display: none;
		}

		.footer__legal {
			flex-direction: column;
		}
	}
</style>
