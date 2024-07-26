<script setup>
defineProps(['label', 'list'])
</script>
<template>
  <select  name="cores" id="cores">
    <option value="" disabled selected>{{ label }}</option>
    <option :value="i.id" v-for="i in list" :key="i.id">
      {{ i?.nome? i?.nome: i?.descricao }}
    </option>
  </select>
</template>
<style scoped>

  select {
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

select:invalid {
  color: rgb(255, 255, 255); 
}


@media (max-width: 1200px) {
  select {
    width: calc(100% - 2vw); 
    font-size: 0.9rem; 
  }
}

@media (max-width: 768px) {
  select {
    width: calc(100% - 2vw); 
    font-size: 0.8rem; 
  }
}

@media (max-width: 480px) {
  select {
    width: calc(100% - 3vw);
    font-size: 0.8rem; 
   
  }
}

</style>
