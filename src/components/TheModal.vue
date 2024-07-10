<script setup>
defineProps({
    title: String,
    timeAttribute: String,
    timeText: String,
    srcImg: String,
    technologies: Array,
    seeProject: String,
    linkGitHub: String
  });

</script>

<template>
    <div class="bloc-modal">
        <div class="overlay" @click="$emit('closeModal')"></div>
        <main>
            <button type="button" @click="$emit('closeModal')">X</button>
            <h2>{{title}}</h2>
            <time :datetime="timeAttribute">{{timeText}}</time>
            <img :src="srcImg" alt="Image représentant le projet">
            <p>Technologies utilisées :</p>
            <ul>
                <li v-for="n in technologies.length">
                    {{technologies[n-1]}}
                </li>
            </ul>
            <div>
                <a :href="seeProject" target="_blank">Voir le projet</a>
                <a :href="linkGitHub" target="_blank" v-if="linkGitHub != '#'">Se rendre au dépôt GitHub</a>
                <div v-if="linkGitHub == '#'"></div>
            </div>
        </main>
    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Alkatra:wght@400..700&display=swap');

.bloc-modal {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.overlay {
    background: rgba(0,0,0,0.5);
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    margin: 0;
}

main {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 600px;
    border: 1px solid #F6994B;
    z-index: 10;
    border-radius: 10px;
    box-shadow: 0 0 1.2rem #F6994B, 0 0 0.2rem #F6994B, 0 0 0.5rem #F6994B;
}

button {
    margin: 10px 10px 0 0;
    align-self: end;
    font-weight: bold;
    border-radius: 50%;
    height: 30px;
    width: 30px;
}

button:hover {
    cursor: pointer;
}

h2 {
    margin: 0;
    font-family: 'Alkatra', Arial, sans-serif;
    font-size: 1.7rem;
}

time {
    margin: 10px 0;
    font-family: 'Alkatra', Arial, sans-serif;
    font-size: 1rem;
}

img {
    width: 350px;
    height: 200px;
    object-fit: contain;
}

ul {
    margin: 0;
    padding: 0;
}

li {
    list-style: none;
    text-align: center;
    font-family: 'Alkatra', Arial, sans-serif;
    font-size: 1rem;
}

p {
    margin: 15px 0 5px 0;
    font-family: 'Alkatra', Arial, sans-serif;
    font-size: 1rem;
    text-decoration: underline;
}

main>div {
    display: flex;
    justify-content: center;
    width: 100%;
    margin-top: 10px;
    padding-left: 90px;
    box-sizing: border-box;
    column-gap: 150px;
}

a {
    text-decoration: none;
    font-family: 'Alkatra', Arial, sans-serif;
    font-size: 1rem;
}

a:hover {
    text-decoration: underline;
}

main div div {
    width: 176px;
}
</style>