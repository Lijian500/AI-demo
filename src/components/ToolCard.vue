<template>
  <div class="bg-white bg-opacity-10 p-4 rounded-lg hover:bg-opacity-20 cursor-pointer">
    <div class="text-2xl mb-2">{{ icon }}</div>
    <h3 class="font-bold text-white mb-1">{{ name }}</h3>
    <p class="text-sm text-gray-200">{{ description }}</p>
  </div>
</template>

<script setup>
defineProps({
  icon: {
    type: String,
    required: true
  },
  name: {
    type: String,
    required: true
  },
  description: {
    type: String,
    required: true
  }
})
</script>

<style scoped>

</style>