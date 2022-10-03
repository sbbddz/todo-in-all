<script lang="ts">
  interface Todo {
    id: number;
    value: string;
  }

  let todos: Todo[] = [];
  let todo: string = '';

  const addTodo = () => {
    if (!todo) return;

    todos = [...todos, {id: todos.length + 1, value: todo}]
    todo = ''
  }

  const removeTodo = (todo: Todo) => {
    todos = todos.filter(x => x.id !== todo.id)
  }
</script>

<main>
  <h1>SvelteDO</h1>
  <form on:submit|preventDefault={addTodo}>
    <input type="text" name="" id="" bind:value={todo} />
  </form>

  <ul>
    {#each todos as t }
      <div style="display: flex; flex-direction: row; align-items: center;">
        <button on:click={() => removeTodo(t)}>Remove</button>
        <li style="list-style-type: none; margin-left: 15px;">{t.value}</li>
      </div>
    {/each}
  </ul>
</main>

<style>
</style>
