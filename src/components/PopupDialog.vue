<template>
  <div v-if="show" class="fixed inset-0 bg-black bg-opacity-50 flex justify-center items-center">
    <div class="bg-white p-6 rounded shadow-lg">
      <slot />
      <button @click="$emit('close')" class="mt-4 bg-blue-500 text-white px-4 py-2 rounded">Tutup</button>
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps({
  show: Boolean
})
</script>
