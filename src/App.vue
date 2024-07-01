<script setup>
import TheHeader from './components/TheHeader.vue'
import ThePresentation from './components/ThePresentation.vue';
</script>

<template>
  <header>
    <TheHeader/>
  </header>
  <main>
    <ThePresentation/>
  </main>
  
</template>

<style>
main {
  background-color: rgb(219, 234, 239);
}
</style>
