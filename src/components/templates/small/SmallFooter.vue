<script setup>
import { ref } from 'vue';
import { onBeforeRouteUpdate } from 'vue-router';

const showMenu = ref(false);

onBeforeRouteUpdate(() => {
  showMenu.value = false;
});
</script>

<template>
  <div id="footerMenu" :style="{ display: showMenu ? 'block' : 'none' }">
    <RouterLink to="/">
      <i class="mdi mdi-home-outline" />
      Home
    </RouterLink>
    <RouterLink to="/login">
      <i class="mdi mdi-account" />
      Login
    </RouterLink>
  </div>
  <div class="icons">
    <RouterLink to="/acessorios" class="icon-link">
      <i class="icon mdi mdi-tire" />
      <span class="tooltip">Acessórios</span>
    </RouterLink>
    <RouterLink to="/categorias" class="icon-link">
      <i class="mdi mdi-car-convertible" />
      <span class="tooltip">Categorias</span>
    </RouterLink>
    <RouterLink to="/cores" class="icon-link">
      <i class="icon mdi mdi-palette" />
      <span class="tooltip">Cores</span>
    </RouterLink>
    <RouterLink to="/marcas" class="icon-link">
      <i class="icon mdi mdi-watermark" />
      <span class="tooltip">Marcas</span>
    </RouterLink>
    <RouterLink to="/modelos" class="icon-link">
      <i class="icon mdi mdi-van-passenger" />
      <span class="tooltip">Modelos</span>
    </RouterLink>
    <RouterLink to="/veiculos" class="icon-link">
      <i class="icon mdi mdi-car-back" />
      <span class="tooltip">Veículos</span>
    </RouterLink>

    <div class="hamburger" @click="showMenu = !showMenu">
      <i class="mdi mdi-menu" />
    </div>
  </div>
</template>

<style scoped>
#footerMenu {
  position: fixed;
  bottom: 12%;
  right: 1rem;
  border-top: #eeeeee 1px solid;
  background-color:#B6B6B6;
  display: block;
  padding: 1rem;
  border-radius: 0.3rem;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
}

#footerMenu a {
  display: flex;
  width: 100%;
  justify-content: space-between;
  text-decoration: none;
  color: #ffffff;
  font-size: 1rem;
  transition: color 0.3s, background-color 0.3s;
}

#footerMenu a:hover {
  color: #333333;
  background-color: #f0f0f0;
  padding: 0.3rem;
}

.icons {
  display: flex;
  width: 100%;
  align-items: center;
  justify-content: space-between;
  position: relative;
}

.icon-link {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-decoration: none;
  color: #282828;
  font-size: 1rem;
  transition: color 0.3s, background-color 0.3s, transform 0.3s;
  padding: 0.5rem;
  position: relative;
}

.icon-link:hover {
  color: #ffffff;
  background-color: #B6B6B6;
  transform: scale(1.1);
}

.tooltip {
  display: none;
  position: absolute;
  bottom: 70px;
  left: 50%;
  transform: translateX(-50%);
  color: #ffffff;
  padding: 0.3rem;
  border-radius: 0.3rem;
  font-size: 0.75rem;
  white-space: nowrap;
  z-index: 10;
  background-color:#B6B6B6;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;

}

.icon-link:hover .tooltip {
  display: block;
}

.hamburger {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-decoration: none;
  color: #282828;
  font-size: 1rem;
  cursor: pointer;
  transition: color 0.3s, background-color 0.3s, transform 0.3s;
  padding: 0.5rem;
}

.hamburger:hover {
  color: #ffffff;
  background-color: #B6B6B6;
  transform: scale(1.1);
}
</style>
