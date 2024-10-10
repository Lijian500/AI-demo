<template>
  <div class="flex items-center space-x-2 p-2 hover:bg-gray-800 rounded cursor-pointer">
    <component :is="icon" class="h-5 w-5" />
    <span>{{ text }}</span>
  </div>
</template>

<script setup>
defineProps({
  icon: {
    type: Object,
    required: true
  },
  text: {
    type: String,
    required: true
  }
})
</script>

<style scoped>

</style>