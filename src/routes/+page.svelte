<script>
    import { onMount } from 'svelte';
    import TodoItem from '../lib/components/TodoItem.svelte';
    import Icon from '@iconify/svelte';
  
    let todos = [];
    let newTodo = '';
  
    onMount(() => {
      const storedTodos = localStorage.getItem('todos');
      if (storedTodos) {
        todos = JSON.parse(storedTodos);
      }
    });
  
    function addTodo() {
      if (newTodo.trim()) {
        todos = [...todos, { id: Date.now(), text: newTodo, completed: false }];
        newTodo = '';
        saveTodos();
      }
    }
  
    function deleteTodo(id) {
      todos = todos.filter(todo => todo.id !== id);
      saveTodos();
    }
  
    function toggleTodo(id) {
      todos = todos.map(todo =>
        todo.id === id ? { ...todo, completed: !todo.completed } : todo
      );
      saveTodos();
    }
  
    function saveTodos() {
      localStorage.setItem('todos', JSON.stringify(todos));
    }
  </script>
  
  <main class="container mx-auto p-4 max-w-md">
    <h1 class="text-3xl font-bold mb-4 text-center text-gray-800">Todo List</h1>
    <form on:submit|preventDefault={addTodo} class="mb-4 flex">
      <input
        bind:value={newTodo}
        placeholder="Add a new todo"
        class="flex-grow p-2 border rounded-l focus:outline-none focus:ring-2 focus:ring-blue-500"
      />
      <button
        type="submit"
        class="bg-blue-500 text-white p-2 rounded-r hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-500"
      >
        <Icon icon="mdi:plus" class="w-6 h-6" />
      </button>
    </form>
    <ul class="space-y-2">
      {#each todos as todo (todo.id)}
        <TodoItem {todo} on:delete={() => deleteTodo(todo.id)} on:toggle={() => toggleTodo(todo.id)} />
      {/each}
    </ul>
  </main>
