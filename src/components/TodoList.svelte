 <script>
     import TodoItem from './TodoItem.svelte'
     let input = ''
     let list = ['a','b']
     const addItem = () => {
        console.log()
        if (!list.includes(input)){
            list = [...list, input]
        }
        console.log(list)
     }
     const handleInput = (event) => {
         input = event.target.value
     }
     const handleDelete = (index) => {
        list.splice(index,1)
        list = list
     }
 </script>

 <style>
     .container {
         margin: auto;
         width: 60%;
     }
     .center {
        padding: 10px;
        background-color: #f44336;
    }
 </style>
 
 <div class='container'>
     <div class='center'>
         <h1>Todo List</h1>
         <input on:input={handleInput} placeholder="Title..."/>
         <button on:click={addItem}>Add</button>
     </div>
     {#each list as item, i}
         <TodoItem value={item} index={i} handleDelete={handleDelete}/>
     {/each}
 </div>