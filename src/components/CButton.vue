<template>
  <button
    type="submit"
    class="bg-blue-500 rounded p-1 mb-5 focus:outline-none text-white"
    @submit="$emit('submit')"
  >
    <slot />
  </button>
</template>
