<template>
  <div>
    <h1 @click="updateTime()">{{ message }}</h1>
  </div>
</template>

<script setup>
import { ref } from 'vue'
let message = ref('')
async function updateTime() {
  message.value = await $fetch('/api/hello')
}
await updateTime()
setInterval(updateTime, 1000);
</script>