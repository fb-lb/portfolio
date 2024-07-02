<script setup></script>

<template>
    <main>
        <h1>Présentation</h1>
        <div>
            <img src="../assets/img/photoPresentation.jpg" alt="Photo de présentation de Fabien Lubre à l'extérieur, homme de brun vue de face portant une paire de lunette">
        </div>
        <p>Je suis actuellement en formation pour l'obtention du titre professionnel de développeur web et web mobile au centre européen de formation. J'ai toujours été attiré par l'informatique d'une manière générale mais ce n'est que récemment que je me suis initié au développement informatique.</p>
        <p>J'ai d'abord suivi un cursus pour devenir docteur vétérinaire mais au cours de ma formation je me suis rendu compte que je n'atteindrais pas un épanouissement professionnel en exerçant ce métier. Etant de nature à aller au bout des choses, j'ai décidé dans un premier temps de terminer ma formation de docteur vétérinaire. Cela m'a permis de prendre le temps de réflexion suffisant pour trouver une alternative professionnelle qui me permette d'obtenir la satisfaction que je recherche.</p>
        <p>Le plaisir que j'ai à suivre ma formation actuelle me conforte dans ma décision de ré-orientation professionnelle. J'ai déjà pu utiliser mes connaissances dans différents projets que je vous partage ci-dessous.</p>
    </main>
    
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Alkatra:wght@400..700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Sriracha&display=swap');

main {
    display: flex;
    flex-direction: column;
    align-items: center;
}

h1 {
    font-family: 'Alkatra', Arial, sans-serif;
    font-size: 2rem;
}

img {
    width: 200px;
    height: 200px;
    object-fit: cover;
    border-radius: 50%;
    box-shadow: 0 0 1.2rem #F6994B, 0 0 0.2rem #F6994B, 0 0 0.5rem #F6994B;
}

p {
    width: 50%;
    text-align: center;
    font-family: 'Sriracha','Alkatra', Arial, sans-serif;
    font-size: 1rem;
    margin : 32px 0 0 0;
}
</style>