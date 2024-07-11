<script setup>
import { RouterLink, RouterView } from 'vue-router'
import TheHeader from './components/TheHeader.vue';
import TheFooter from './components/TheFooter.vue';


</script>

<template>
  <header>
    <TheHeader/>
  </header>
  <main>
    <RouterView/>
  </main> 
  <footer>
    <TheFooter/>
  </footer>
</template>

<style scoped>
header {
  position: sticky;
  top: 0px;
}
</style>

<style>
:root {
  --header-height: 113px;
}

* {
  scroll-behavior: smooth;
}

.scroll {
  scroll-margin-top: calc(var(--header-height) - 30px);
}
</style>
