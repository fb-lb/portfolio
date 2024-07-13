<script setup>
import { ref } from 'vue';
import { onMounted } from 'vue';

let isErrorTextVisible = ref(false);
let errorMessage = ref("");
let mail = import.meta.env.VITE_EMAIL;

let fullName = ref("");
let email = ref("");
let subject = ref("");
let message = ref("");

onMounted(()=>{
    let form = document.querySelector("form");
    
    form.onsubmit = (event)=>{
        // Checking validity of the fields on submission
        if (fullName.value.trim() == "" || email.value.trim() == "" || subject.value.trim() == "" || message.value.trim() == "") {
            fullName.value = fullName.value.trim();
            email.value = email.value.trim();
            subject.value = subject.value.trim();
            message.value = message.value.trim();
            isErrorTextVisible.value = true;
            errorMessage.value = "Merci de bien vouloir remplir tous les champs";
            event.preventDefault();
        } else if (!email.value.includes('@')) {
            isErrorTextVisible.value = true;
            errorMessage.value = "L'E-mail doit contenir le caractère '@'";
            event.preventDefault();
        } else if (email.value.startsWith('@')) {
            isErrorTextVisible.value = true;
            errorMessage.value = "L'E-mail doit contenir une partie précédent le caractère '@'";
            event.preventDefault();
        } else if (email.value.endsWith('@')) {
            isErrorTextVisible.value = true;
            errorMessage.value = "L'E-mail doit contenir une partie suivant le caractère '@'";
            event.preventDefault();
        } else if (email.value.indexOf('@') != email.value.lastIndexOf('@')) {
            isErrorTextVisible.value = true;
            errorMessage.value = "L'E-mail doit contenir un seul caractère '@'";
            event.preventDefault();
        } else {
            isErrorTextVisible.value = false;
            fullName.value = "";
            email.value = "";
            subject.value = "";
            message.value = "";
            alert("Merci, votre mail a bien été envoyé à " + mail);
            return false;
        };
    };
});
</script>

<template>
    <div id="contactForm">
        <h2>Contact</h2>
        <form action="#" method="post">
            <div>
                <label for="fullName">Nom Prénom</label>
                <input type="text" name="fullName" id="fullName" maxlength="40" v-model="fullName">
            </div>
            <div>
                <label for="email">E-mail</label>
                <input type="email" name="email" id="email" maxlength="40" v-model="email">
            </div>
            <div>
                <label for="subject">Objet du mail</label>
                <input type="text" name="subject" id="subject" maxlength="60" v-model="subject">
            </div>
            <textarea name="message" id="message" rows="7" cols="60" placeholder="Votre message" maxlength="1000" v-model="message"></textarea>
            <small>Maximum : 1 000 caractères</small>
            <p v-if="isErrorTextVisible">{{errorMessage}}</p>
            <button type="submit">Envoyer</button>
        </form>
    </div>    
</template>

<style scoped>
#contactForm {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: rgb(204, 214, 223);
    width: 100%;
    margin: 0;
}

form {
    display: flex;
    flex-direction: column;
    align-items: center;
}

h2 {
    font-family: 'Alkatra', Arial, sans-serif;
    font-size: 1.7rem;
    border-top: double 4px rgb(235, 143, 67);
    padding-top: 25px;
    margin: 50px 0 20px 0;
    width: 50%;
    text-align: center;
}

div {
    margin: 0 0 20px 0;
    display: flex;
    justify-content: space-between;
    width: 283px;
}

label {
    font-family: 'Sriracha', Arial, sans-serif;
    font-size: 1rem;
    width: 94px;
    text-align: end;
}

textarea {
    margin: 0 0;
}

small {
    margin-bottom: 15px;
    font-family: 'Sriracha', Arial, sans-serif;
    font-size: 0.8rem;
    align-self: flex-start;
}

p {
    font-family: 'Sriracha', Arial, sans-serif;
    font-size: 1rem;
    font-weight: bold;
    margin: 0;
    color: darkred;
}

button {
    font-family: 'Sriracha', Arial, sans-serif;
    font-size: 1rem;
    width: 100px;
    text-align: center;
    margin: 10px 0 40px 0;
}

button:hover {
    cursor: pointer;
}
</style>