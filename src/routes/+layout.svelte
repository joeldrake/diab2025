<script>
	import '$lib/css/reset.css';
	import '$lib/css/colors.css';
	import '$lib/css/style.css';
</script>

<svelte:head>
	<title>Drake Innovation AB</title>

	<meta name="description" content="Drake Innovation AB" />
	<meta property="og:image" content={'/joeldrake.jpg'} />
	<link rel="apple-touch-icon" href="/icon.jpg" />
	<link rel="shortcut icon" href="/icon.jpg" />
</svelte:head>

<slot />
