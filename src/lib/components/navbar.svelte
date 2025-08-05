<script lang="ts">
	import StarOverlay from './starOverlay.svelte';
</script>

<nav class="navbar">
	<a href="/writing" class="nav-link">
		WRITING
		<div class="blinking-cursor"></div>
	</a>

	<a href="/faqs" class="nav-link"> FAQs </a>
	<a href="/editing" class="nav-link">
		EDITING
		<img src="/images/editing_overlay_filled.svg" alt="Editing" class="editing-overlay" />
	</a>

	<a href="/endorsements" class="nav-link">
		ENDORSEMENTS
		<div class="star-container">
			{#each Array(5).fill(0) as _, index}
				<img src="/images/star.svg" alt="Star" class="empty-star" loading="lazy" />
			{/each}
		</div>
	</a>
</nav>

<style>
	.editing-overlay {
		position: absolute;
		top: -1.6em;
		left: -1.7em;
		width: 200%;
		height: 200%;
		z-index: 1;
	}

	.blinking-cursor {
		position: absolute;
		right: -0.1em;
		bottom: 0.5em;
		width: 0.4em;
		height: 0.14em;
		background-color: #26cc17;
		animation: blink 1.5s infinite;
	}

	@keyframes blink {
		0%,
		100% {
			opacity: 1;
		}
		50% {
			opacity: 0;
		}
	}

	.star-container {
		position: absolute;
		top: 1.6em;
		right: 0.5em;
		display: flex; /* Align stars horizontally */
		gap: 0.1em; /* Add spacing between stars */
	}

	.empty-star {
		width: 0.9em; /* Adjust star size */
		height: 0.9em; /* Adjust star size */
	}

	.navbar {
		position: relative;
		display: flex;
		justify-content: space-between;
	}

	.nav-link {
		position: relative;
		color: #333;
		padding: 10px;
		text-decoration: none;
		font-size: 1.6rem;
		font-weight: 900;
		font-family: 'Cabin Condensed', sans-serif;
	}

	.nav-link:hover {
		color: #0070f3;
		text-decoration: underline;
	}
</style>
