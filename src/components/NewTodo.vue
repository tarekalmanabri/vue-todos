<template>
  <div
    class="bg-gray-200 transition-colors duration-700 dark:bg-gray-500 my-5 flex flex-col items-center rounded"
  >
    <div>
      <CustomHeader props:dark-is-active />
      <TodoForm />
      <TodoList />
    </div>
  </div>
</template>

<script>
import CustomHeader from "./CustomHeader.vue";
import TodoList from "./TodoList.vue";
import TodoForm from "./TodoForm.vue";

export default {
  components: {
    CustomHeader,
    TodoList,
    TodoForm,
  },
  data() {
    return {
      darkIsActive: this.$props.darkIsActive,
    };
  },
};
</script>
