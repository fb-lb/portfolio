<script setup>
</script>

<template>
    <main>
        <a href="#"><img src="../assets/img/portfolioIcon2.png" alt="Logo d'un portfolio bleu foncé dans un cercle dont le fond est de couleur bleue claire et le contour orange"></a>
        <nav>
            <ul>
                <li><a href="#">Présentation</a></li>
                <li><a href="#">CV</a></li>
                <li><a href="#">La Socketterie - Cahier des charges</a></li>
                <li><a href="#">Zone de commentaire dynamique</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>
    </main>
    
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Sriracha&display=swap');

main {
    background-color: lightblue;
    display: flex;
    flex-direction: column;
}

main > a {
    align-self: center;
    margin: 10px 0 5px 0;
    clip-path: circle(50%);
}

img {
    width: 90px;
}

nav {
    background-color: #9ABBD9;
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

ul li a:hover {
    text-decoration: underline;
    text-shadow: 0 0 0.2rem #F28749, 0 0 1rem #F28749;
}
</style>