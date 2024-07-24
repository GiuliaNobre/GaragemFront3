<script setup>
import LogoTitle from '@/components/templates/LogoTitle.vue';
</script>
<template>
  <div class="logo_and_menu">
    <logo-title class="mb-2" />
    <div class="divider" />
    <div class="menu">
      <router-link to="/acessorios">
        <i class="icon mdi mdi-tire" /> Acessorio
      </router-link>
      <router-link to="/categorias">
        <i class="mdi mdi-car-convertible" /> Categoria
      </router-link>

      <router-link to="/cores">
        <i class="icon mdi mdi-palette" /> Cor
      </router-link>
      <router-link to="/marcas">
        <i class="icon mdi mdi-watermark" /> Marca
      </router-link>
      <router-link to="/modelos">
        <i class="icon mdi mdi-van-passenger" /> Modelo
      </router-link>
      <router-link to="/veiculos">
        <i class="icon mdi mdi-car-back" /> Veiculo
      </router-link>
      <router-link to="/login">
        <i class="icon mdi mdi-account" /> Login
      </router-link>
      
    </div>
  </div>

  
</template>
<style scoped>
.mb-2 {
  margin-bottom: 1.5rem;
}

.icon {
  font-size: 2rem;
  align-self: center;
}

.divider {
  margin-top: 1rem;
  border-top: 1px solid #eeeeee;
}

.menu {
  padding: 3rem;
}

.menu a {
  display: flex;
  align-items: center;
  text-decoration: none;
  color: #000000;
  gap: 1rem;
  font-size: 1.3rem;
  margin-top: 2.2rem;
}
</style>
  