<template>
  <input
    class="w-full transition-colors duration-700 bg-white dark:bg-gray-700 m-5 rounded p-2"
    v-bind="$props"
    @input="$emit('input', $event.target.value)"
  />
</template>

<script>
export default {
  name: 'CInput',
  props: {
    // eslint-disable-next-line vue/require-prop-types
    value: {
      required: true
    },
    type: {
      type: String,
      default: 'text'
    }
  }
}
</script>
