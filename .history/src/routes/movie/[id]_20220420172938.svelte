<script context="module">
    export async function load({ fetch, params }) {
        const res = await fetch(
            `https://api.themoviedb.org/3/movie/${params.id}?api_key=4414716af6e1ab93f3b8433567170adc`,
        );

        const data = await res.json();
        console.log(data);

        if(res.ok) {
            return {
                props: {
                    movieDetail
                }
            };
        }
    }
</script>

<script>
    export let movieDetail;
</script>

<div class="movie-details">
    <div class="img-container">
        <img src={'https://image.tmdb.org/t/p/original' + movieDetail.poster_path} alt={movieDetail.title} />
    </div>
    <div class="text-container">
        
    </div>
</div>
