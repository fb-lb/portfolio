<script setup></script>

<template>
    <div class="errorPage">
      <img src="/src/assets/img//erreurPage.png" alt="">
      <p>404</p>
      <p>Oops ! Cette page est introuvable</p>
      <a href="/">Retour à la page d'accueil</a>
    </div>
</template>
  
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Alkatra:wght@400..700&display=swap');

.errorPage {
  background-color: rgb(204, 214, 223);
  padding-top: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

img {
  width: 200px;
}

p {
  font-family: 'Alkatra', Arial, sans-serif;
  font-size: 1.7rem;
  margin: 0;
  font-weight: bold;
  text-align: center;
  text-shadow: #F28749 0px 2px, #F28749 -2px 0px, #F28749 2px 0px,#F28749 0px -2px;
}

p:first-of-type {
  font-size: 2.5rem;
}

a {
  font-family: 'Alkatra', Arial, sans-serif;
  font-size: 1.2rem;
  font-weight: bold;
  text-decoration: none;
  color: black;
  text-align: center;
  margin: 50px 0;
}

</style>
  