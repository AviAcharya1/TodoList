<script>
    import { createEventDispatcher } from 'svelte';
    import Icon from '@iconify/svelte';
  
    export let todo;
    const dispatch = createEventDispatcher();
  </script>
  
  <li class="flex items-center bg-white p-3 rounded shadow-sm transition-all duration-200 hover:shadow-md">
    <input
      type="checkbox"
      checked={todo.completed}
      on:change={() => dispatch('toggle')}
      class="mr-3 form-checkbox h-5 w-5 text-blue-500 rounded focus:ring-blue-500"
    />
    <span class={todo.completed ? 'line-through text-gray-500 flex-grow' : 'flex-grow'}>
      {todo.text}
    </span>
    <button
      on:click={() => dispatch('delete')}
      class="text-red-500 hover:text-red-700 focus:outline-none"
    >
      <Icon icon="mdi:delete" class="w-6 h-6" />
    </button>
  </li>