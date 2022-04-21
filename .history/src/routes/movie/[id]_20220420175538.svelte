<script context="module">
    export async function load({ fetch, params }) {
        const res = await fetch(
            `https://api.themoviedb.org/3/movie/${params.id}?api_key=4414716af6e1ab93f3b8433567170adc`,
        );

        const movieDetail = await res.json();

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
    console.log(movieDetail);
</script>

<div class="movie-details">
    <div class="img-container">
        <img src={'https://image.tmdb.org/t/p/original' + movieDetail.backdrop_path} alt={movieDetail.title} />
    </div>
    <div class="text-container">
        <h1> {movieDetail.title} </h1>
        <p class="overview"> {movieDetail.overview} </p>
        <p><span> Release Date : </span>
            &nbsp; {movieDetail.release_date} <br />
            <span> Budget : </span>
            &nbsp; ${movieDetail.budget} <br />
            <span> Rating : </span>
            &nbsp; {movieDetail.vote_average} <br />
            <span> Runtime : </span>
            &nbsp; {movieDetail.runtime} min.
        </p>
    </div>
</div>

<style>
    h1 {
        padding: 1rem 0 2rem;
    }

    p {
        padding: 1rem 0;
    }

    .img-container {
        width: 100%;
    }

    img {
        width: 100%;
        border-radius: 1rem;
    }

    .movie-details {
        margin: 2rem 20%;
    }

    span {
        font-weight: bold;
    }
</style>
