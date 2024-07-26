<script setup>
import { defineEmits } from 'vue';
const emit = defineEmits([])
</script>
<template>
    <input type="number">
</template>
<style scoped>
input {
  padding: 0.5rem; 
  border-radius: 50px; 
  border: 1px solid #797e8c;
  outline: none;
  box-sizing: border-box;
  font-size: 0.9rem; 
  width: 100%;
  max-width: 200px; 
  height: auto;
}
</style>