<script setup></script>

<template>
    <div class="footer">
        <div>
            <a href="https://fr.linkedin.com/" target="_blank"><img  class="icons__linkedin" src="/src/assets/img/socialNetworkIcons.png" alt="Icône de Linkedin"></a>
            <a href="https://github.com/fb-lb" target="_blank"><img class="icons__github" src="/src/assets/img/socialNetworkIcons.png" alt="Icône de GitHub"></a>
            <a href="https://www.facebook.com/fabien.lubre" target="_blank"><img class="icons__facebook" src="/src/assets/img/socialNetworkIcons.png" alt="Icône de Facebook"></a>
        </div>
        <small>Mis à jour le <time datetime="2024-07-11">11/07/2024</time></small>
    </div>
</template>

<style scoped>
.footer{
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: rgb(164, 205, 219);
    border-top: 5px solid rgb(146, 176, 197);
    margin: 0;
}

div div {
    display: flex;
    gap: 20px;
    margin: 20px 0;
}

a {
    width: 50px;
    height: 50px;
    overflow: hidden;
    border-radius: 50%;
}

img {
    height: 50px;
    width: 150px;
    object-fit: cover;
}

.icons__linkedin {
    object-position:top;
    background-color: black;
}

.icons__linkedin:hover {
    background-color: rgb(247, 150, 70);
}

.icons__github {
    object-position:top 0 left -50px;
}

.icons__github:hover {
    object-position:bottom 0 left -50px;
}

.icons__facebook {
    object-position:top 0 left -100px;
}

.icons__facebook:hover {
    object-position:bottom 0 left -100px;
}

small {
    margin-bottom: 20px;
    font-family: 'Sriracha', Arial, sans-serif;
    font-size: 0.8rem
}
</style>