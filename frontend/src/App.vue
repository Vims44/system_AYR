<script setup>
import { ref, onMounted } from 'vue'

const message = ref('загрузка...')

onMounted(async () => {
  const res = await fetch('http://localhost:3000/api/test')
  const data = await res.json()
  message.value = data.message
})
</script>

<template>
  <div style="padding: 20px">
    <h1>Vue + Backend</h1>
    <p>{{ message }}</p>
  </div>
</template>