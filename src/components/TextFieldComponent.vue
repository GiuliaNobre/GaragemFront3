<script setup>
defineProps(["label"]);
const model = defineModel();
</script>
<template>
  <span class="input-container">
    <input type="text" :placeholder="label" v-model="model" />
  </span>
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

@media (max-width: 1200px) {
  input {
    padding: 0.5rem; 
    width: calc(100% - 2vw);
    font-size: 0.9rem; 
  }
}

@media (max-width: 768px) {
  input {
    padding: 1vw; 
    width: calc(100% - 2vw); 
    font-size: 0.8rem; 
  }
}

@media (max-width: 480px) {
  input {
    padding: 1.2vw; 
    width: calc(100% - 3vw); 
    font-size: 0.8rem;
  }
}

</style>