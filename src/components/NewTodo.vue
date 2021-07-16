<template>
  <div
    class="bg-gray-200 transition-colors duration-700 dark:bg-gray-500 my-5 flex flex-col items-center rounded"
  >
    <div>
      <Header props:dark-is-active />
      <TodoForm />
      <Todos />
    </div>
  </div>
</template>

<script>
import Header from "./Header.vue";
import Todos from "./Todos.vue";
import TodoForm from "./TodoForm.vue";

export default {
  components: {
    Header,
    Todos,
    TodoForm,
  },
  data() {
    return {
      darkIsActive: this.$props.darkIsActive,
    };
  },
};
</script>
