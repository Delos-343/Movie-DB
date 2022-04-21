

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<a href="/about">About</a>
<button>Click Me!</button>

<script>
    import PopularMovies from "src/components/PopularMovies.svelte";
    export let popular;
</script>

<section>
    <PopularMovies />
</section>