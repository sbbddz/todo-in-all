<script lang="ts">
  interface Todo {
    id: number;
    value: string;
  }

  let todos: Todo[] = JSON.parse(window.localStorage.getItem("svelteTODOS")) ?? [];
  let todo: string = '';

  const addTodo = () => {
    if (!todo) return;

    todos = [...todos, {id: todos.length + 1, value: todo}]
    todo = ''
    updateTodosInLocalStorage();
  }

  const removeTodo = (todo: Todo) => {
    todos = todos.filter(x => x.id !== todo.id)
    updateTodosInLocalStorage();
  }

  const updateTodosInLocalStorage = () => {
    window.localStorage.setItem("svelteTODOS", JSON.stringify(todos))
  }
</script>

<main>
  <h1>SvelteDO</h1>
  <form on:submit|preventDefault={addTodo}>
    <input type="text" name="" id="" bind:value={todo} />
  </form>

  <ul>
    {#each todos as t }
      <div id="todo" style="display: flex; flex-direction: row; align-items: center;">
        <button on:click={() => removeTodo(t)}>Remove</button>
        <li style="list-style-type: none; margin-left: 15px;">{t.value}</li>
      </div>
    {/each}
  </ul>
</main>

<style>
  input {
    padding: 10px;
    font-size: 1.75em;
  }

  h1 {
    font-size: 4em;
  }

  #todo {
    font-size: 1.5em;
    margin-top: 15px;
    transition: transform 0.2s ease;
  }

  #todo:hover {
    cursor: pointer;
    transform: translateY(-5px);
  }
</style>
