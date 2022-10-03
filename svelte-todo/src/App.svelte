<script lang="ts">
  let todos: string[] = [];
  let todo: string = '';

  const addTodo = () => {
    if (!todo) return;

    todos = [...todos, todo]
    todo = ''
  }
</script>

<main>
  <h1>SvelteDO</h1>
  <form on:submit|preventDefault={addTodo}>
    <input type="text" name="" id="" bind:value={todo} />
  </form>

  <ul class="list">
    {#each todos as t }
      <li>{t}</li>
    {/each}
  </ul>
</main>

<style>
</style>
