<script>
    import MovieCard from "./MovieCard.svelte";
    export let popular;
</script>

<h3> Popular Movies </h3>

<div class="popular-movies">
    {#each popular as movie }
        <MovieCard />
    {/each}
</div>
