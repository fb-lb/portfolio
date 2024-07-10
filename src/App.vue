<script setup>
import { ref } from 'vue';
import TheHeader from './components/TheHeader.vue';
import ThePresentation from './components/ThePresentation.vue';
import TheProject from './components/TheProject.vue';
import TheModal from './components/TheModal.vue';
import ContactForm from './components/ContactForm.vue';
import TheFooter from './components/TheFooter.vue';

let isModalCvActive = ref(false);
let isModalSocketterieActive = ref(false);
let isModalDynamicCommentActive = ref(false);

let myCv = {
  title: "Mon CV",
  srcImg: "/src/assets/img/imageCv.jpg",
  id: "myCv",
  openModal: ()=>{isModalCvActive.value = true}
};

let theSocketterie = {
  title: "La Socketterie - Cahier des charges",
  srcImg: "/src/assets/img/logoSocketterie.jpg",
  id: "theSocketterie",
  openModal: ()=>{isModalSocketterieActive.value = true}
};

let dynamicComment = {
  title: "Zone de commentaire dynamique",
  srcImg: "/src/assets/img/commentairesDynamiques.jpg",
  id: "dynamicComment",
  openModal: ()=>{isModalDynamicCommentActive.value = true}
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

let projectList = [myCv, theSocketterie, dynamicComment];

</script>

<template>
  <header>
    <TheHeader/>
  </header>
  <main>
    <ThePresentation class="scroll"/>
    <TheProject v-for="project in projectList"
      :title="project.title"
      :srcImg="project.srcImg"
      :id="project.id"
      @open-modal="project.openModal"
      class="scroll"/>
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
