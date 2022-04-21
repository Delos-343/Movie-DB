<script context="module">
    
    export async function load({fetch}) {
        const res = await fetch(
            `https://api.themoviedb.org/3/movie/popular?api_key=4414716af6e1ab93f3b8433567170adc`,
        );

        const data = await res.json();
        
        if(res.ok) {
            return {
                props: {
                    popular: data.results
                }
            };
        }
    }

</script>

<script>
    import PopularMovies from "src/components/PopularMovies.svelte";
    export let popular;
</script>

<section>
    <PopularMovies {popular} />
</section>