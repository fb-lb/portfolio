<script setup>
import { ref } from 'vue';

let isThePresentationActive = ref(false);
let isMyCvActive = ref(false);
let isTheSocketterieActive = ref(false);
let isDynamicCommentActive = ref(false);
let isContactFormActive = ref(false);

function noActiveLink() {
    isThePresentationActive.value = false;
    isMyCvActive.value = false;
    isTheSocketterieActive.value = false;
    isDynamicCommentActive.value = false;
    isContactFormActive.value = false;
}

function activeLink(link) {
    noActiveLink();
    switch (link) {
        case "activeThePresentation" :
            isThePresentationActive.value=true;
            break;
        case "activeMyCv" :
            isMyCvActive.value=true;
            break;
        case "activeTheSocketterie" :
            isTheSocketterieActive.value=true;
            break; 
        case "activeDynamicComment" :
            isDynamicCommentActive.value=true;
            break;
        case "activeContactForm" :
            isContactFormActive.value=true;
            break;
    }
}
</script>


<template >
    <div class="header">
        <a href="/#" @click="noActiveLink()"><img src="../assets/img/portfolio.png" alt="Logo d'un portfolio bleu foncé dans un cercle dont le fond est de couleur bleue claire et le contour orange"></a>
        <div>      
            <h1>Portfolio de Fabien Lubre</h1>
            <nav>
                <ul>
                    <li><a href="/#presentation" :class="{active: isThePresentationActive}" @click="activeLink('activeThePresentation')">Présentation</a></li>
                    <li><a href="/#myCv" :class="{active: isMyCvActive}" @click="activeLink('activeMyCv')">CV</a></li>
                    <li><a href="/#theSocketterie" :class="{active: isTheSocketterieActive}" @click="activeLink('activeTheSocketterie')">La Socketterie - Cahier des charges</a></li>
                    <li><a href="/#dynamicComment" :class="{active: isDynamicCommentActive}" @click="activeLink('activeDynamicComment')">Zone de commentaire dynamique</a></li>
                    <li><a href="/#contactForm" :class="{active: isContactFormActive}" @click="activeLink('activeContactForm')">Contact</a></li>
                </ul>
            </nav>
        </div>
    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Alkatra:wght@400..700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Sriracha&display=swap');

.header {
    background-color: rgb(164, 205, 219);
    display: flex;
}

.header > a {
    align-self: center;
    margin: 10px 10px 5px 10px;
    clip-path: circle(50%);
}

img {
    width: 90px; 
}

.header div {
    display: flex;
    flex-direction: column;
    width: 100%;
}

h1 {
    text-align: center;
    padding-right: 110px;
    font-family: 'Alkatra', Arial, sans-serif;
    font-size: 2rem;
    margin: 10px 0;
    text-shadow: 0 0 0.2rem #F28749, 0 0 1rem #F28749;
}

nav {
    background-color: rgb(146, 176, 197);
}

ul {
    display: flex;
    justify-content: space-around;
    list-style: none;
    margin: 5px 0;
    padding: 0;
}

li {
    text-align: center;
    display: flex;
}

ul li a {
    align-self: center;
    font-family: 'Sriracha', Arial, sans-serif;
    text-decoration: none;
    color: black;
    font-size: 1rem;
}

.active {
    text-decoration: underline;
}

ul li a:hover {
    text-shadow: 0 0 0.2rem #F28749, 0 0 1rem #F28749;
}
</style>