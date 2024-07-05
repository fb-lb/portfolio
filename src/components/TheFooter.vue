<script setup></script>

<template>
    <main>
        <div>
            <a href="https://fr.linkedin.com/" target="_blank"><img  class="icons__linkedin" src="/src/assets/img/socialNetworkIcons.png" alt=""></a>
            <a href="https://github.com/fb-lb" target="_blank"><img class="icons__github" src="/src/assets/img/socialNetworkIcons.png" alt=""></a>
            <a href="https://www.facebook.com/fabien.lubre" target="_blank"><img class="icons__facebook" src="/src/assets/img/socialNetworkIcons.png" alt=""></a>
        </div>
        <small>Dernière mise à jour le <time datetime="2024-07-05">05/07/2024</time></small>
    </main>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Sriracha&display=swap');

main {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: lightblue;
    border-top: 5px solid #9ABBD9;
}

div {
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
    background-color: #F6994B;
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