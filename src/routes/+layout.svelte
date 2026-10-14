<script>
	import { injectSpeedInsights } from '@vercel/speed-insights';
	import { inject, pageview } from '@vercel/analytics';
	import { browser, dev } from '$app/env';
	import { afterNavigate } from '$app/navigation';
	import '#lib/css/reset.css';
	import '#lib/css/openProps.css';
	import '#lib/css/colors.css';
	import '#lib/css/style.css';

	// The @vercel/*/sveltekit wrappers import `$app/stores`, which SvelteKit 3 removed,
	// so we wire up the generic APIs ourselves and report routes via afterNavigate.
	const speedInsights = browser ? injectSpeedInsights({ framework: 'sveltekit' }) : null;

	if (browser) {
		inject({
			mode: dev ? 'development' : 'production',
			disableAutoTrack: true,
			framework: 'sveltekit'
		});
	}

	afterNavigate(({ to }) => {
		if (!to?.route.id) return;
		pageview({ route: to.route.id, path: to.url.pathname });
		speedInsights?.setRoute(to.route.id);
	});
</script>

<svelte:head>
	<title>Drake Innovation AB</title>

	<meta name="format-detection" content="telephone=no" />

	<meta name="description" content="Drake Innovation AB" />
	<meta property="og:image" content={'/joeldrake.jpg'} />
	<link rel="apple-touch-icon" href="/icon.jpg" />
	<link rel="shortcut icon" href="/icon.jpg" />
</svelte:head>

<slot />
