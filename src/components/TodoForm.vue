<template>
  <form
    class="bg-gray-100 transition-colors duration-700 dark:bg-gray-800 my-5 p-3 flex flex-col items-center rounded container"
    @submit.prevent="addTodo"
  >
    <CInput ref="text" v-model="todo" />
    <CSelect v-model="priority" :options="priorities" />
    <CSelect v-model="assignee" :options="assignees" />
    <CButton>
      submit
    </CButton>
  </form>
</template>

<script>
import CButton from './CButton'
import CInput from './CInput'
import CSelect from './CSelect.vue'

export default {
  components: {
    CButton,
    CInput,
    CSelect
  },

  data() {
    return {
      todo: null,
      priority: 'medium',
      assignee: 'null',

      priorities: [
        {
          text: 'Low',
          value: 'low'
        },
        {
          text: 'Medium',
          value: 'medium'
        },
        {
          text: 'High',
          value: 'high'
        }
      ],
      assignees: [
        {
          text: 'Unassigned',
          value: 'null'
        },
        {
          text: 'Tarek',
          value: 'tarek'
        },
        {
          text: 'Mocha',
          value: 'mocha'
        },
        {
          text: 'Edie',
          value: 'edie'
        },
        {
          text: 'Gouda',
          value: 'gouda'
        }
      ]
    }
  },
  methods: {
    addTodo() {
      if (!this.todo) {
        alert('Please add a new task')
        return
      } else {
        this.$emit('add-todo', {
          todo: this.todo,
          priority: this.priorities.find(
            (priority) => priority.value === this.priority
          ).text,
          assignee: this.assignees.find(
            (assignee) => assignee.value === this.assignee
          ).text,
          done: false
        })
      }
      this.$refs.text.$el.focus()

      this.todo = null
    }
  }
}
</script>
