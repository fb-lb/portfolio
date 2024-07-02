<script setup>
import TheHeader from './components/TheHeader.vue'
import ThePresentation from './components/ThePresentation.vue';
import TheProject from './components/TheProject.vue';

let myCv = {
  title: "Mon CV",
  srcImg: "/src/assets/img/imageCv.jpg"
};

let theSocketterie = {
  title: "La Socketterie - Cahier des charges",
  srcImg: "/src/assets/img/logoSocketterie.jpg"
};

let dynamicComment = {
  title: "Zone de commentaire dynamique",
  srcImg: "/src/assets/img/commentairesDynamiques.jpg"
};

</script>

<template>
  <header>
    <TheHeader/>
  </header>
  <main>
    <ThePresentation/>
    <TheProject :title="myCv.title" :srcImg="myCv.srcImg"/>
    <TheProject :title="theSocketterie.title" :srcImg="theSocketterie.srcImg"/>
    <TheProject :title="dynamicComment.title" :srcImg="dynamicComment.srcImg"/>
  </main>
  
</template>

<style>
main {
  background-color: rgb(219, 234, 239);
}
</style>
