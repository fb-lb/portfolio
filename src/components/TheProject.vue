<script setup>
defineProps({
  title: String,
  srcImg: String
});
</script>

<template>
    <div class="project">
        <h2>{{title}}</h2>
        <img :src="srcImg" @click="$emit('openModal')" alt="Image du CV">
    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Alkatra:wght@400..700&display=swap');

.project {
    display: flex;
    flex-direction:column;
    align-items: center;
    background-color: rgb(219, 234, 239);
}

h2 {
    border-top: double 4px #F28749;
    padding-top: 25px;
    margin: 50px 0 20px 0;
    font-family: 'Alkatra', Arial, sans-serif;
    font-size: 1.7rem;
    width: 50%;
    text-align: center;
}

img {
    width: auto;
    height: auto;
    max-width: 250px;
    max-height: 300px;
}

img:hover {
    cursor: pointer;
}
</style>