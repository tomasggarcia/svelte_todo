 <script>
     import TodoItem from './TodoItem.svelte'
     let input = ''
     let values = ['a','b']
     let status = [true,false]
     const addItem = () => {
        console.log()
        if (!values.includes(input)){
            values = [...values, input]
            status = [...status, true]
        }
        console.log(values)
     }
     const handleInput = (event) => {
         input = event.target.value
     }
     const handleDelete = (index) => {
        values.splice(index,1)
        values = values
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
         <h1>Todo values</h1>
         <input on:input={handleInput} placeholder="Title..."/>
         <button on:click={addItem}>Add</button>
     </div>
     {#each values as item, i}
         <TodoItem value={item} index={i} handleDelete={handleDelete} status={status[i]}/>
     {/each}
 </div>