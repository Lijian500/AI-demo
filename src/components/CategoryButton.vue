<template>
  <button
      class="px-4 py-2 rounded-full"
      :class="isActive ? 'bg-red-500 text-white' : 'bg-gray-200 bg-opacity-30 text-white'">
    {{ text }}
  </button>
</template>

<script setup>
defineProps({
  text: {
    type: String,
    required: true
  },
  isActive: {
    type: Boolean,
    default: false
  }
})
</script>

<style scoped>

</style>