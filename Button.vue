<script setup>
  defineProps({
    type: {
      type: String,
      default: 'light'
    }
  })
</script>
<template>
  <button type="button" class="inline-flex items-center px-4 py-2 text-sm font-medium text-gray-700 bg-white border border-gray-300 rounded-md shadow-sm hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2" :class="type">
    <slot />
  </button>
</template>
<style scoped>
  button.action{
    @apply fixed p-3 text-white flex items-center justify-center rounded-full z-[999999] bottom-10 right-8 drop-shadow-lg hover:bg-blue-700 hover:drop-shadow-2xl;
  }
  button.primary{
    @apply bg-indigo-600 text-white hover:bg-indigo-700 focus:ring-indigo-500;
  }
  button.warning{
    @apply bg-orange-500 text-white hover:bg-orange-700 focus:ring-orange-500;
  }
  button.danger{
    @apply bg-rose-500 text-white hover:bg-rose-700 focus:ring-rose-500;
  }
</style>
