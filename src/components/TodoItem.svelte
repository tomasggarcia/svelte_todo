<script>
    import FaCheck from 'svelte-icons/fa/FaCheck.svelte'
    export let value
    export let index
    export let handleDelete
    export let status
    let checked = !status

    const check = () => {
        checked = !checked
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
        background-color: grey;
    }
    .crossOut p {
        text-decoration: line-through;
    }

    .check {
        display: inline-block;
        transform: rotate(45deg);
        height: var(--height);
        width: var(--width);
        border-bottom: var(--borderWidth) solid var(--borderColor);
        border-right: var(--borderWidth) solid var(--borderColor);
    }
    .icon {
        padding: 7px;
        width: 20px;
        height: 20px;
        background-color: grey;
    }
</style>

<div on:click={check} class="{checked?'crossOut':''}">
    {#if checked}
    <div class='icon'>
        <FaCheck/>
    </div>
    <div class="check"></div>
    {/if}
    <p>{value}</p>
    <button on:click={() => handleDelete(index)}>x</button>
</div>