<script>
    let inputValue = '';
    let active = false;

    function cancelInactive() {
        if(inputValue) {
            active = true;
        } else {
            active = false;
        }
    }
</script>

<form class="search">
    {#if !active}
        <label for="search_movie"> Search Movie </label>
    {/if}
    <input on:blur={cancelInactive} on:focus={() => (active = true)} bind:value={inputValue} name="search_movie" type="text" />
    {#if inputValue}
        <button> Search </button>
    {/if}
</form>

<style>
    .search {
        position: relative;
        width: 30%;
        margin: 1rem;
    }

    button {
        font-size: 0.7rem;
        padding: 0 1rem;
        background: rgb(96, 110, 201);
        color: #dcdcdc;
        font-weight: bold;
        border: none;
        position: absolute;
        bottom: 50%;
        right: 0;
        transform: translate(0, 50%);
        height: 100%;
        border-top-right-radius: 10px;
        border-bottom-right-radius: 10px;
        cursor: pointer;
    }

    input {
        width: 100%;
        border: none;
        font-size: 1rem;
        font-family: 'Poppins', sans-serif;
        outline: none;
        color: rgb(255, 255, 255);
        padding: 0.5rem 0.1rem;
        transition: background 0.75s ease-out;
        font-weight: bold;
        background: rgb(63, 63, 63);
        border-radius: 10px;
        padding: 1rem;
    }

    label {
        position: absolute;
        font-size: 0.8rem;
        top: 50%;
        left: 0;
        transform: translate(0, -50%);
        pointer-events: none;
        color: #eee;
        padding: 0 1rem;
    }

    input.selected {
        background: rgb(50, 50, 50);
    }
</style>
