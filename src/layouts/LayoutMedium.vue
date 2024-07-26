<script setup>
  import MediumAside from '@/components/templates/medium/MediumAside.vue';
</script>

<template>
  <div id="layout-medium">
  
    <aside>
      <medium-aside />
    </aside>
    <main>
      <router-view />
    </main>
  </div>
</template>

<style scoped>
#layout-medium {
  display: grid;
  grid-template-columns: 1fr 6fr;
  grid-template-rows: auto 1fr auto;
  grid-template-areas:
    'aside main';
  min-height: 100vh;
}
aside {
  border-right: #eeeeee 1px solid;
  box-shadow: 0 0 10px 0 #eeeeee;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding-top: 1.5rem;
  padding-bottom: 1.5rem;
  grid-area: aside;
}

main {
  min-height: 80%;
  padding: 2rem;
  grid-area: main;
}


</style>