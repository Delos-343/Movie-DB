<script context="module">
    export async function load({ fetch }) {
        const res = await fetch(
            `https://api.themoviedb.org/3/movie/popular?api_key=4414716af6e1ab93f3b8433567170adc`,
        );

        const data = await res.json();
        console.log(data);

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
    import PopularMovies from "../components/PopularMovies.svelte";
    import SearchMovies from "../components/SearchMovies.svelte";
    import { fly } from 'svelte/transition';
    export let popular;
</script>

<section in:fly={{ y: 50, duration: 500 }}>
    <SearchMovies />
    <PopularMovies {popular} />
</section>
