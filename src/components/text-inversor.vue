<script setup>
import { computed, ref } from 'vue'

const message = ref('')
const reversedMessage = computed(() => {
  return message.value.split('').reverse().join('')
})
</script>

<template>
  <div class="container">
    <h1>Inversor de Texto</h1>
    <input v-model="message" type="text" placeholder="Digite algo..." />
    <p class="result-title">Resultado</p>
    <p class="result">{{ reversedMessage || "O texto invertido aparecerá aqui..." }}</p>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  width: 100%;
  gap: 1rem;
  flex-direction: column;

  border-radius: 12px;
}

h1 {
  font-size: 1.8rem;
  color: hsla(160, 100%, 37%, 1);
  font-weight: 800;
}

input {
  width: 100%;
  padding: 12px;
  font-size: 1rem;
  border: var(--color-border);
  border-radius: 8px;
  outline: none;
  transition: border-color 0.3s, box-shadow 0.3s;
}

input:focus {
  border-color: var(--color-border);
}

.result-title {
  font-size: 1.4rem;
  font-weight: 600;
  color: hsla(160, 100%, 37%, 1);
}

.result {
  word-break: break-word;
  padding: 1rem;
  background: var(--color-background-soft);
  border-radius: 1rem;
}
</style>
