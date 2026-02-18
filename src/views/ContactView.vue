<script setup>
import { ref } from 'vue'

const nom = ref('')
const email = ref('')
const message = ref('')
</script>

<template>
  <div class="contact">
    <h1>Contactez-moi</h1>
    
    <form @submit.prevent="alert('Message envoyé !')">
      <div>
        <label>Nom :</label>
        <input v-model="nom" type="text" required>
      </div>
      
      <div>
        <label>Email :</label>
        <input v-model="email" type="email" required>
      </div>
      
      <div>
        <label>Message :</label>
        <textarea v-model="message" required></textarea>
      </div>
      
      <button type="submit">Envoyer</button>
    </form>
    
    <router-link to="/">← Retour</router-link>
  </div>
</template>

<style scoped>
.contact {
  max-width: 500px;
  margin: 0 auto;
  padding: 2rem;
}
form div {
  margin-bottom: 1rem;
}
label {
  display: block;
  margin-bottom: 0.5rem;
}
input, textarea {
  width: 100%;
  padding: 0.5rem;
}
button {
  background-color: #42b883;
  color: white;
  padding: 0.5rem 1rem;
  border: none;
  cursor: pointer;
}
</style>