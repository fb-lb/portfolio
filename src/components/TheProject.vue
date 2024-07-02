<script setup>
import { ref } from 'vue'
defineProps({
  title: String,
  srcImg: String
});

</script>

<template>
    <main>
        <h1>{{title}}</h1>
        <img :src="srcImg" alt="Image du CV">
        
    </main>
    
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Alkatra:wght@400..700&display=swap');

main {
    display: flex;
    flex-direction:column;
    align-items: center;
}

h1 {
    border-top: double 4px #F28749;
    padding-top: 25px;
    margin: 50px 0 20px 0;
    font-family: 'Alkatra', Arial, sans-serif;
    font-size: 2rem;
    width: 50%;
    text-align: center;
}

img {
    width: 250px;
    height: 300px;
    object-fit:contain;
}
</style>