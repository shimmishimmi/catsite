<script lang="ts">
	let { children } = $props();
	import 'normalize.css/normalize.css';
	import Navbar from '$lib/components/navbar.svelte';
	import Hamburger from '$lib/components/hamburger.svelte';
	import Footer from '$lib/components/footer.svelte';
	import { onMount } from 'svelte';

	let pageWidth = $state(800);

	function updatePageWidth() {
		pageWidth = window.innerWidth;
	}

	onMount(() => {
		updatePageWidth();
	});

	$effect(() => {
		window.addEventListener('resize', updatePageWidth);
	});
</script>

<div class="container">
	<h1 class="title {pageWidth < 600 ? 'mobile' : ''}">
		<a href="/" class="title-link">Words by Cat</a>
	</h1>

	<!-- </h1> -->
	{#if pageWidth < 600}
		<Hamburger />
	{:else}
		<Navbar />
	{/if}

	{@render children()}

	<Footer />
</div>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Cabin+Condensed:wght@400;500;600;700&family=Geist:wght@100..900&display=swap');
	@import url('https://fonts.googleapis.com/css2?family=Pacifico&display=swap');
	@import url('https://fonts.googleapis.com/css2?family=Mr+De+Haviland&display=swap');
	@import url('https://fonts.googleapis.com/css2?family=Mr+De+Haviland&family=Zhi+Mang+Xing&display=swap');
	@import url('https://fonts.googleapis.com/css2?family=Monoton&display=swap');

	:global(h1, h2, h3, h4, h5, h6) {
		color: #222222;
		font-weight: 500;
		font-family: 'Cabin Condensed', sans-serif;
	}

	:global(body) {
		background-color: #ffffff;
	}

	h1.title {
		/* font-size: 5rem; */
		font-size: 5.5rem;
		/* font-weight: 900; */
		/* font-family: 'Pacifico', cursive; */
		/* font-family: 'Zhi Mang Xing', cursive; */
		/* font-family: 'Mr De Haviland', cursive; */
		font-family: 'Monoton', sans-serif;
		margin-bottom: 0.1em;
		margin-top: 0.5em;
		/* font-family: 'Cabin Condensed', sans-serif; */
		color: #222222;
		/* justify */
		text-align: center;
		word-spacing: 0.2em;
	}

	.title-link {
		text-decoration: none;
		color: #222222;
		transition: color 0.3s ease-in-out;
	}

	.title-link:hover {
		/* text-decoration: underline; */
		color: #0070f3;
	}

	h1.title.mobile {
		font-size: 3rem;
		text-align: left;
		margin-left: 0em;
		margin-top: 0em;
	}

	:global(h1) {
		font-size: 2.5rem;
	}

	:global(h2) {
		font-size: 2rem;
	}

	:global(p) {
		color: #333333;
		font-size: 1.2rem;
		font-family: 'Geist', sans-serif;
		font-weight: 300;
		line-height: 1.6;
	}

	:global(hr) {
		border: none;
		border-top: 1px solid #ccc;
		margin: 2em 0;
	}

	.container {
		max-width: 800px;
		margin: 0 auto;
		padding: 1rem;
		margin-bottom: 0;
		padding-bottom: 0;
	}
</style>
