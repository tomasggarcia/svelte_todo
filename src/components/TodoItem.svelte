<script>
    export let value
    export let index
    export let handleDelete
    export let status
    let hasLineThrough = !status

    const lineThrough = () => {
        hasLineThrough = !hasLineThrough
    }
</script>

<style>
    div {
        display: flex;
        background-color: white;
        
    }
    button {
        margin-left: auto;
    }

    .crossOut {
        text-decoration: line-through;
    }
</style>

<div on:click={lineThrough} >
    <p class="{hasLineThrough?'crossOut':''}">{value}</p>
    <button on:click={() => handleDelete(index)}>x</button>
</div>