<script setup>
defineProps({
  title: String,
  srcImg: String,
  altImg: String
});
</script>

<template>
    <div>
        <h2>{{title}}</h2>
        <img :src="srcImg" @click="$emit('openModal')" :alt="altImg">
    </div>
</template>

<style scoped>
div {
    display: flex;
    flex-direction:column;
    align-items: center;
    background-color: rgb(204, 214, 223);
}

h2 {
    border-top: double 4px rgb(247, 150, 70);
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
    box-shadow: 7px 7px 0.2rem rgb(247, 150, 70), 7px 7px 0.7rem rgb(247, 150, 70);
}
</style>