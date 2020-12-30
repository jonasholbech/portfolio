<script>
	import Nav from "./Nav.svelte";
	import Header from "./Header.svelte";
	import AboutMe from "./AboutMe.svelte";
	import Resume from "./Resume.svelte";
</script>

<style>
	/* @media (min-width: 640px) {
		main {
			max-width: none;
		}
	} */
</style>

<Nav />
<main>
	<Header />
	<AboutMe />
	<Resume />
</main>
