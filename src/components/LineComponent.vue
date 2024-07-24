<script setup>
import { defineEmits } from 'vue';
const emit = defineEmits(['excluir'])

</script>
<template>
  <ul>
    <li v-for="veiculo in veiculos" :key="veiculo.id">
      <span @click="editar(veiculo)">
        ({{ veiculo.id }}) - {{ veiculo.ano }} - {{ veiculo.preco }} - {{ veiculo.cor }} -
        {{ veiculo.modelo }} - {{ veiculo.acessorio }}
      </span>
      <button class="bt-delete" @click="$emit('excluir')(veiculo.id)">X</button>
    </li>
  </ul>
</template>
<style scoped>
</style>