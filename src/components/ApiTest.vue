//ApiTest.vue
<template>
    <div>   
        <h1>Api Test</h1>
        <button @click="testApi">Check Connection to Backend</button>
        <p v-if="message">{{ message }}</p>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import api from '@/services/api'

const message = ref('')

const testApi = async () => {
  try {
    const response = await api.get('/')
    message.value = response.data.message
  } catch (error) {
    message.value = `Error: Unable to connect to backend > ${error}`
  }
}

</script>