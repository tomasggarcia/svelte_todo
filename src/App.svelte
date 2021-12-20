<script lang="ts">
    import TodoList from './components/TodoList.svelte'
    let num = 1;
    let handleClick = () => {
        num ++
    }
</script>


<h1>{num}</h1>
<button on:click={handleClick}>+1</button>

<TodoList/>