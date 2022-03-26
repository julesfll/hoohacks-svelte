<script>
  export let todo;
  import { fly } from 'svelte/transition';
</script>

<li transition:fly={{y: 50, duration: 500}}>
  <input type="checkbox" bind:checked={todo.done}>
  {todo.text}
</li>

<style>
  li {
    list-style-type: none;
  }
</style>