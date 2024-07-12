<script setup>
import { ref } from 'vue';
import { onMounted } from 'vue';

let isErrorTextVisible = ref(false);
let actionForm = ref('');
let mail = import.meta.env.VITE_EMAIL;

onMounted(()=>{
    let form = document.querySelector("form");
    let fullName = document.getElementById("fullName");
    let subject = document.getElementById("subject");
    let message = document.getElementById("message");
    
    form.onsubmit = (event)=>{
        // Checking validity of the fields on submission
        if (fullName.value.trim() == "" || subject.value.trim() == "" || message.value.trim() == "") {
            fullName.value = fullName.value.trim();
            subject.value = subject.value.trim();
            message.value = message.value.trim();
            isErrorTextVisible.value = true;
            event.preventDefault();
        } else {
            isErrorTextVisible.value = false;
            actionForm.value = "mailto:" + mail + "?subject=" + document.getElementById('subject').value + "&body=" + document.getElementById('message').value;
            form.reset(); 
            alert("Merci, votre mail a bien été envoyé à " + mail);  
        };
    };
});
</script>

<template>
    <div id="contactForm">
        <h2>Contact</h2>
        <form :action="actionForm" method="post">
            <div>
                <label for="fullName">Nom Prénom</label>
                <input type="text" name="fullName" id="fullName">
            </div>
            <div>
                <label for="subject">Objet du mail</label>
                <input type="text" name="subject" id="subject">
            </div>
            <textarea name="message" id="message" rows="7" cols="60" placeholder="Votre message" maxlength="1000"></textarea>
            <small>Maximum : 1 000 caractères</small>
            <p v-if="isErrorTextVisible">Merci de bien vouloir remplir tous les champs</p>
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