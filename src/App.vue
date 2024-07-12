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
@import url('https://fonts.googleapis.com/css2?family=Alkatra:wght@400..700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Sriracha&display=swap');

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
