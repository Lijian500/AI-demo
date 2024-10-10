<template>
  <button
      class="px-4 py-2 text-white"
      :class="{ 'border-b-2 border-white': isActive }">
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