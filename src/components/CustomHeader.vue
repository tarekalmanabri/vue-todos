<template>
  <div class="flex flex-col">
    <h1 class="p-3 font-bold">
      Add new todo
    </h1>
    <button class="mb-2 focus:outline-none" @click="toggleMode">
      <i v-if="darkIsActive" class="fas fa-moon" />
      <i v-else class="fas fa-sun" />
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      darkIsActive: localStorage.theme === 'dark'
    }
  },

  methods: {
    toggleMode() {
      if (this.darkIsActive) {
        localStorage.theme = 'light'
        document.documentElement.classList.remove('dark')
      } else {
        localStorage.theme = 'dark'
        document.documentElement.classList.add('dark')
      }

      this.darkIsActive = !this.darkIsActive
    }
  }
}
</script>
