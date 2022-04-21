<script>
    export let movie;
</script>

<div class="movie-card">
    <a href={'/movie/' + movie.id}>
        <img src={'https://image.tmdb.org/t/p/w500' + movie.poster_path} alt={movie.title} />
    </a>
    <div class="description">
        <h2> {movie.title} </h2>
        <p class="desc"> {movie.overview} </p>
        <p> {movie.release_date} </p>
    </div>
</div>

<style>
    img {
        width: 100%;
        object-fit: cover;
        border-radius: 1rem;
        margin-bottom: 1rem;
    }

    h2 {
        font-size: 0.9rem;
    }

    .description {
        height: 5vh;
    }

    p {
        font-size: 0.7rem;
    }

    .movie-card {
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        padding: 1rem;
    }

    .desc {
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
        margin: 0.5rem 0 1rem 0;
    }
</style>
