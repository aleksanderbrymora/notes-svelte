<script>
    export let notes;
    export let handleClick, createNew;
</script>

<style>
    p {
        cursor: pointer;
        color: white;
    }
    nav {
        background-color: blue;
        margin: 0;
        height: 100vh;
    }
    button {
        background-color: white;
        padding: 0.5rem 1rem;
        border: none;
        border-radius: 15px;
        cursor: pointer;
    }
</style>

<nav>
    <h1>NotAble</h1>
    <button on:click={createNew}>Create new</button>
    <h2>Your notes</h2>
    {#each notes as note}
        <p on:click={() => handleClick(note.id)}>{note.title}</p>
    {/each}
</nav>