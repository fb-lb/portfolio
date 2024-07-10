<script setup>
import { ref } from 'vue';
import { onMounted } from 'vue';

let isErrorTextVisible = ref(false);
let actionForm = ref('');

onMounted(()=>{
    let form = document.querySelector("form");
    let lastName = document.getElementById("lastName");
    let firstName = document.getElementById("firstName");
    let subject = document.getElementById("subject");
    let message = document.getElementById("message");
    
    form.onsubmit = (event)=>{
        // Checking validity of the fields on submission
        if (lastName.value.trim() == "" || firstName.value.trim() == "" ||  subject.value.trim() == "" || message.value.trim() == "") {
            lastName.value = lastName.value.trim();
            firstName.value = firstName.value.trim();
            subject.value = subject.value.trim();
            message.value = message.value.trim();
            isErrorTextVisible.value = true;
            event.preventDefault();
        } else {
            isErrorTextVisible.value = false;
            actionForm.value = "mailto:fb.lubre@free.fr?subject=" + document.getElementById('subject').value + "&body=" + document.getElementById('message').value;
            form.reset();   
        };
    };
});
</script>

<template>
    <main id="contactForm">
        <h2>Contact</h2>
        <form :action="actionForm" method="post">
            <div>
                <label for="lastName">Nom</label>
                <input type="text" name="lastName" id="lastName">
            </div>
            <div>
                <label for="firstName">Prénom</label>
                <input type="text" name="firstName" id="firstName">
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
    </main>    
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Alkatra:wght@400..700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Sriracha&display=swap');

main {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: rgb(219, 234, 239);
}

form {
    display: flex;
    flex-direction: column;
    align-items: center;
}

h2 {
    font-family: 'Alkatra', Arial, sans-serif;
    font-size: 1.7rem;
    border-top: double 4px #F28749;
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