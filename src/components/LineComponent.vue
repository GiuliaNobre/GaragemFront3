<script setup>
defineProps(['veiculos'])
const model = defineModel();
</script>
<template>
  <ul>
    <li v-for="veiculo in veiculos" :key="veiculo.id">
      <span @click="(veiculo)">
        ({{ veiculo.id }}) - {{ veiculo.ano }} - {{ veiculo.preco }} - {{ veiculo.cor }} -
        {{ veiculo.modelo }} - {{ veiculo.acessorio }}
      </span>
      <button class="bt-delete" @click="$emit('excluir', veiculo.id)">X</button>
    </li>
  </ul>
</template>
<style scoped>
ul {
  padding: 0;
  width: 100%; 
  list-style: none; 
  margin-top: 1rem;
}
li {
  background-color: #fff;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px; 
  margin: 0.5rem 0; 
  border-radius: 4px; 
  display: flex;
  justify-content: space-between;
  align-items: center; 
  padding: 0.6rem 1rem; 
}


@media (max-width: 1200px) {
  li {
    margin-top: 0.5rem;
  padding: 0.6rem 1rem;
  }
}
@media (max-width: 768px) {
  li {
  margin-top: 0.5rem;
  padding: 0.6rem 1rem; 
  }
}

@media (max-width: 480px) {
  li {
  margin-top: 0.5rem;
  padding: 0.6rem 1rem; 
  }
}

</style>
