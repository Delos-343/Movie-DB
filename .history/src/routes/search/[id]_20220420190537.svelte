<script context="module">
    export async function load({ fetch, params }) {
        const res = await fetch(
            `https://api.themoviedb.org/3/movie/${params.id}&page=1&include_adult=false`,
        );

        const data = await res.json();

        if(res.ok) {
            return {
                props: {
                    searchedMovie: data.results
                }
            };
        }
    }
</script>