<script>
    export let value
    export let index
    export let handleDelete
</script>

<style>
    div {
        display: flex;
        background-color: white;
        
    }
    button {
        margin-left: auto;
    }
</style>

<div>
    <p>{value}</p>
    <button on:click={() => handleDelete(index)}>x</button>
</div>