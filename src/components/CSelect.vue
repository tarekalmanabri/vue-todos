<template>
  <select
    :value="value"
    class="w-full m-5 rounded bg-white transition-colors duration-700 dark:bg-gray-700 p-2"
    @change="$emit('change', $event.target.value)"
  >
    <option
      v-for="option in options"
      :key="option.value"
      :value="option.value"
      v-text="option.text"
    />
  </select>
</template>

<script>
export default {
  model: {
    prop: 'value',
    event: 'change'
  },
  props: {
    // eslint-disable-next-line vue/require-prop-types
    value: {
      required: true
    },
    options: {
      type: Array,
      default: null
    }
  }
}
</script>
