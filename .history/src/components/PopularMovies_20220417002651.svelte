<script>
    export let popular;
</script>

<h3>PopularMovies.section( img, caption )</h3>
<div class="popular-movies">
    {#each popular as movie}
    <h1> {movie} </h1>
    {/each}
</div>