<div class="star-container">
	{#each Array(5).fill(0) as _, index}
		<img src="/images/star.svg" alt="Star" class="empty-star" loading="lazy" />
	{/each}
</div>

<style>
	.star-container {
		display: flex; /* Align stars horizontally */
		gap: 0.1em; /* Add spacing between stars */
	}
	.empty-star {
		width: 0.9em; /* Adjust star size */
		height: 0.9em; /* Adjust star size */
	}
</style>
