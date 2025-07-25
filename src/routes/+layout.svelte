<script lang="ts">
	let { children } = $props();
	import 'normalize.css/normalize.css';
</script>

<div class="container">
	<h1 class="title">Words by Cat</h1>
	{@render children()}
</div>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Cabin+Condensed:wght@400;500;600;700&family=Geist:wght@100..900&display=swap');
	:global(h1, h2, h3, h4, h5, h6) {
		color: #222222;
		font-weight: 600;
		font-family: 'Cabin Condensed', sans-serif;
	}

	h1 {
		font-size: 2.5rem;
	}

	h2 {
		font-size: 2rem;
	}

	h1 .title {
		font-size: 2.5rem;
		font-weight: 600;
		font-family: 'Cabin Condensed', sans-serif;
	}

	:global(p) {
		color: #333333;
		font-size: 1.2rem;
		font-family: 'Geist', sans-serif;
		font-weight: 300;
		line-height: 1.6;
	}

	.container {
		max-width: 800px;
		margin: 0 auto;
		padding: 1rem;
	}
</style>
