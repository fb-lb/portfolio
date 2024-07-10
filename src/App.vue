<script setup>
import { ref } from 'vue';
import TheHeader from './components/TheHeader.vue';
import ThePresentation from './components/ThePresentation.vue';
import TheProject from './components/TheProject.vue';
import TheModal from './components/TheModal.vue';
import ContactForm from './components/ContactForm.vue';
import TheFooter from './components/TheFooter.vue';

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

let modalCv = {
  title: "Mon CV",
  timeAttribute: "2024-04-21",
  timeText: "21/04/2024",
  srcImg: "/src/assets/img/imageCv.jpg",
  technologies: ["HTML", "CSS"],
  seeProject: "/src/assets/projects/cvLubre/index.html",
  linkGitHub: "https://github.com/fb-lb/cv_Lubre"
};

let modalSocketterie = {
  title: "La Socketterie - Cahier des charges",
  timeAttribute: "2024-05-23",
  timeText: "23/05/2024",
  srcImg: "/src/assets/img/logoSocketterie.jpg",
  technologies: ["Word", "Adobe Acrobat"],
  seeProject: "/src/assets/projects/Cahier_des_charges_La_Socketterie.pdf",
  linkGitHub: "#"
};

let modalDynamicComment = {
  title: "Zone de commentaire dynamique",
  timeAttribute: "2024-06-12",
  timeText: "12/06/2024",
  srcImg: "/src/assets/img/commentairesDynamiques.jpg",
  technologies: ["HTML", "JavaScript"],
  seeProject: "/src/assets/projects/commentaire_dynamique/index.html",
  linkGitHub: "https://github.com/fb-lb/commentaire_dynamique"
};

let isModalCvActive = ref(false);
let isModalSocketterieActive = ref(false);
let isModalDynamicCommentActive = ref(false);

</script>

<template>
  <header>
    <TheHeader/>
  </header>
  <main>
    <ThePresentation class="scroll"/>
    <TheProject :title="myCv.title" :srcImg="myCv.srcImg" @open-modal="isModalCvActive = true" id="myCv" class="scroll"/>
    <TheProject :title="theSocketterie.title" :srcImg="theSocketterie.srcImg" @open-modal="isModalSocketterieActive = true" id="theSocketterie" class="scroll"/>
    <TheProject :title="dynamicComment.title" :srcImg="dynamicComment.srcImg" @open-modal="isModalDynamicCommentActive = true" id="dynamicComment" class="scroll"/>
    <teleport to=#modals>
       <TheModal :title="modalCv.title" :timeAttribute="modalCv.timeAttribute" :timeText="modalCv.timeText" :srcImg="modalCv.srcImg" :technologies="modalCv.technologies" :seeProject="modalCv.seeProject" :linkGitHub="modalCv.linkGitHub" v-if="isModalCvActive" @close-modal="isModalCvActive = false"/>
       <TheModal :title="modalSocketterie.title" :timeAttribute="modalSocketterie.timeAttribute" :timeText="modalSocketterie.timeText" :srcImg="modalSocketterie.srcImg" :technologies="modalSocketterie.technologies" :seeProject="modalSocketterie.seeProject" :linkGitHub="modalSocketterie.linkGitHub" v-if="isModalSocketterieActive" @close-modal="isModalSocketterieActive = false"/>
       <TheModal :title="modalDynamicComment.title" :timeAttribute="modalDynamicComment.timeAttribute" :timeText="modalDynamicComment.timeText" :srcImg="modalDynamicComment.srcImg" :technologies="modalDynamicComment.technologies" :seeProject="modalDynamicComment.seeProject" :linkGitHub="modalDynamicComment.linkGitHub" v-if="isModalDynamicCommentActive" @close-modal="isModalDynamicCommentActive = false"/>
    </teleport>
    <ContactForm class="scroll"/>
  </main>
  <footer>
    <TheFooter/>
  </footer>
</template>

<style>
:root {
  --header-height: 113px;
}

* {
  scroll-behavior: smooth;
}

main {
  background-color: rgb(219, 234, 239);
}

.scroll {
  scroll-margin-top: calc(var(--header-height) - 30px);
}

header {
  position: sticky;
  top: 0px;
}
</style>
