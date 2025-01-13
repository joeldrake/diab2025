<script>
	import { injectSpeedInsights } from '@vercel/speed-insights/sveltekit';
	import { injectAnalytics } from '@vercel/analytics/sveltekit';
	import '$lib/css/reset.css';
	import '$lib/css/openProps.css';
	import '$lib/css/colors.css';
	import '$lib/css/style.css';

	injectSpeedInsights();

	injectAnalytics();
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
