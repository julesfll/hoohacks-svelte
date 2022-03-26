<script>
  import Item from "./Item.svelte";
  
    let todos = [
      { done: false, text: 'Make a to-do list'}
    ];
    let value;
  
    function handleSubmit() {
      todos = [...todos, { done: false, text: value }];
    }
  
    $: filtered = todos.filter(todo => !todo.done);
  </script>
  
  <h1>To-do List</h1>
  <p>{filtered.length} items left</p>
  
  {#each filtered as todo}
    <Item bind:todo />
  {:else}
    <p>Add a to-do!</p>
  {/each}
  
  <form on:submit|preventDefault={handleSubmit}>
    <input bind:value/>
  </form>
  <button on:click={handleSubmit}>Add to-do</button>