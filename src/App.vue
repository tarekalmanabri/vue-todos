<template>
  <div class="flex flex-col items-center">
    <CustomHeader />
    <TodoForm @add-todo="addTodo" />
    <TodoList :todos="todos" />
  </div>
</template>

<script>
import TodoList from './components/TodoList'
import CustomHeader from './components/CustomHeader.vue'
import TodoForm from './components/TodoForm.vue'

export default {
  components: {
    TodoList,
    CustomHeader,
    TodoForm
  },

  data() {
    return {
      todos: []
    }
  },

  methods: {
    addTodo(todo) {
      this.todos.push(todo)
    }
  }
}
</script>
