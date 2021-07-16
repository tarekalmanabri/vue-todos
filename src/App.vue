<template>
  <div class="flex flex-col items-center">
    <Header />
    <TodoForm @add-todo="addTodo" />
    <Todos :todos="todos" />
  </div>
</template>

<script>
import Todos from './components/Todos'
import Header from './components/Header.vue'
import TodoForm from './components/TodoForm.vue'

export default {
  components: {
    Todos,
    Header,
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
