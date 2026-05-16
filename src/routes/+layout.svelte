<script>
	import favicon from '$lib/assets/favicon.svg';
	import Header from '$lib/components/Header.svelte';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<meta charset="utf-8" />
	<meta name="viewport" content="width=device-width, initial-scale=1" />
</svelte:head>

<Header />

<main>
	{@render children()}
</main>

<style>
	@import url('https://cdn.jsdelivr.net/gh/orioncactus/pretendard/dist/web/static/pretendard.css');

	:global(body) {
		margin: 0;
		padding: 0;
		font-family: 'Pretendard', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto,
			'Helvetica Neue', Arial, sans-serif;
		color: #333;
		background-color: #fafafa;
		font-feature-settings: 'ss01' on, 'ss02' on;
		text-rendering: optimizeLegibility;
	}

	:global(button),
	:global(input),
	:global(textarea),
	:global(select) {
		font-family: inherit;
	}

	main {
		max-width: 1200px;
		margin: 0 auto;
		padding: 2rem;
	}
</style>
