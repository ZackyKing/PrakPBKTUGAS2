<template>
  <div>
    <h1 :style="headerStyle">Program Web Sederhana dengan Vue.js 3</h1>
    <input 
      :class="{ 'error': isError }" 
      :style="{ 'border-color': isError ? 'red' : 'initial' }" 
      @input="handleInput" 
      v-model="inputText" 
      placeholder="Ketik Sesuatu...">
    <p v-if="isError" class="error-message">Tolong ketik sesuatu!</p>
    <h3>{{ inputText }}</h3>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';

const inputText = ref('');
const isError = computed(() => inputText.value === '');

const handleInput = (event) => {
  inputText.value = event.target.value;
};
</script>

<style scoped>
.error {
  border: 1px solid red;
}
.error-message {
  color: red;
}
</style>
