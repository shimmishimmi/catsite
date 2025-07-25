<script lang="ts">
	let { children } = $props();
</script>

{@render children()}

<style>
	:global(h1) {
		color: red;
		font-size: 2rem;
		margin-bottom: 1rem;
	}
</style>
