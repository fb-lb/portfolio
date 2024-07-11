<script setup>
import { ref } from 'vue';
import { reactive } from 'vue';
import ThePresentation from '../components/ThePresentation.vue';
import TheProject from '../components/TheProject.vue';
import TheModal from '../components/TheModal.vue';
import ContactForm from '../components/ContactForm.vue';

let isModalCvActive = ref(false);
let isModalSocketterieActive = ref(false);
let isModalDynamicCommentActive = ref(false);

// The projects object

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

let projectList = [myCv, theSocketterie, dynamicComment];

// The modals object

let modalCv = reactive({
  title: "Mon CV",
  timeAttribute: "2024-04-21",
  timeText: "21/04/2024",
  srcImg: "/src/assets/img/imageCv.jpg",
  technologies: ["HTML", "CSS"],
  seeProject: "/src/assets/projects/cvLubre/index.html",
  linkGitHub: "https://github.com/fb-lb/cv_Lubre",
  activeModal: isModalCvActive,
  close: ()=>{isModalCvActive.value = false}
});

let modalSocketterie = reactive({
  title: "La Socketterie - Cahier des charges",
  timeAttribute: "2024-05-23",
  timeText: "23/05/2024",
  srcImg: "/src/assets/img/logoSocketterie.jpg",
  technologies: ["Word", "Adobe Acrobat"],
  seeProject: "/src/assets/projects/Cahier_des_charges_La_Socketterie.pdf",
  linkGitHub: "#",
  activeModal: isModalSocketterieActive,
  close: ()=>{isModalSocketterieActive.value = false}
});

let modalDynamicComment = reactive({
  title: "Zone de commentaire dynamique",
  timeAttribute: "2024-06-12",
  timeText: "12/06/2024",
  srcImg: "/src/assets/img/commentairesDynamiques.jpg",
  technologies: ["HTML", "JavaScript"],
  seeProject: "/src/assets/projects/commentaire_dynamique/index.html",
  linkGitHub: "https://github.com/fb-lb/commentaire_dynamique",
  activeModal: isModalDynamicCommentActive,
  close: ()=>{isModalDynamicCommentActive.value = false}
});

let modalList = [modalCv, modalSocketterie, modalDynamicComment];
</script>

<template>
    <ThePresentation class="scroll"/>
    <TheProject v-for="project in projectList"
    :title="project.title"
    :srcImg="project.srcImg"
    :id="project.id"
    @open-modal="project.openModal"
    class="scroll"/>
    <teleport to=#modals v-for="modal in modalList">
        <TheModal v-if="modal.activeModal"
        :title="modal.title"
        :timeAttribute="modal.timeAttribute"
        :timeText="modal.timeText"
        :srcImg="modal.srcImg"
        :technologies="modal.technologies"
        :seeProject="modal.seeProject"
        :linkGitHub="modal.linkGitHub"
        @close-modal="modal.close"/>
    </teleport>
    <ContactForm class="scroll"/>
</template>

<style scoped>
</style>