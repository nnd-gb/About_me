<script setup>
import { ref } from 'vue'

const message = ref('Bienvenue sur mon site Vue.js !')
</script>

<template>
  <main>
    <h1>{{ message }}</h1>
    <p>Ceci est ma page d'accueil géniale construite avec Vue.js</p>
    <router-link to="/about">En savoir plus sur moi →</router-link>
  </main>
</template>

<style scoped>
main {
  text-align: center;
  padding: 2rem;
}
h1 {
  color: #42b883;
}
</style>