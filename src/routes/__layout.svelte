<script lang="ts">
	import Navbar from "../lib/Navbar.svelte";
</script>

<header>
	<Navbar />
</header>

<main>
	<slot />
</main>

<style lang="less">
	:global(*) {
		font-family: Arial, Helvetica, sans-serif;
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}

	main {
		margin-top: 4rem;
	}
</style>