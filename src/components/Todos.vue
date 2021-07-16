<template>
  <ul>
    <li
      v-for="(todo, index) in todos"
      :key="todo.todo + index"
      class="rounded p-3 m-1 bg-gray-100 transition-colors duration-700 dark:bg-gray-800 border-green-400"
      :class="{
        'line-through text-gray-600 border-l-2': todo.done
      }"
      @click="todo.done = !todo.done"
    >
      Task: {{ todo.todo }} - ({{ todo.priority }})
      <template v-if="todo.assignee !== 'null'">
        - Assigned to: {{ todo.assignee }}
      </template>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    todos: {
      type: Array,
      default: null
    }
  }
}
</script>
