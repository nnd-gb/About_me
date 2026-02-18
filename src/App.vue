<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div id="app">
    <header>
      <nav class="navbar">
        <div class="nav-container">
          <router-link to="/" class="logo">
            <img src="./assets/logo.png" alt="Logo" class="nav-logo" />
            <span></span>
          </router-link>
          
          <ul class="nav-menu">
            <li><router-link to="/" class="nav-link">Accueil</router-link></li>
            <li><router-link to="/about" class="nav-link">À propos</router-link></li>
            <li><router-link to="/contact" class="nav-link">Contact</router-link></li>
          </ul>
        </div>
      </nav>
    </header>

    <main>
      <RouterView />
    </main>

    <footer class="footer">
      <div class="footer-content">
        <p>&copy; 2024 NJETCHOU NZEPA Daniel Jordan. Tous droits réservés.</p>
        <div class="footer-links">
          <a href="https://github.com/nnd-gb" target="_blank">GitHub</a>
          <a href="#" target="_blank">LinkedIn</a>
          <a href="#" target="_blank">TryHackMe</a>
        </div>
      </div>
    </footer>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  line-height: 1.6;
  color: #333;
}

#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

/* Navbar Styles */
.navbar {
  background: white;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  position: sticky;
  top: 0;
  z-index: 1000;
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 1rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  text-decoration: none;
  font-size: 1.5rem;
  font-weight: bold;
  color: #667eea;
}

.nav-logo {
  width: 40px;
  height: 40px;
  border-radius: 90%;
}

.nav-menu {
  display: flex;
  list-style: none;
  gap: 2rem;
}

.nav-link {
  text-decoration: none;
  color: #333;
  font-weight: 500;
  transition: color 0.3s;
  padding: 0.5rem 1rem;
  border-radius: 5px;
}

.nav-link:hover {
  color: #667eea;
  background: #f5f5f5;
}

.nav-link.router-link-exact-active {
  color: #667eea;
  background: #f0f0f0;
}

/* Footer Styles */
.footer {
  background: #2c3e50;
  color: white;
  margin-top: auto;
}

.footer-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
  text-align: center;
}

.footer-links {
  margin-top: 1rem;
  display: flex;
  gap: 1.5rem;
  justify-content: center;
}

.footer-links a {
  color: white;
  text-decoration: none;
  opacity: 0.8;
  transition: opacity 0.3s;
}

.footer-links a:hover {
  opacity: 1;
}

@media (max-width: 768px) {
  .nav-menu {
    gap: 1rem;
  }
  
  .nav-link {
    padding: 0.5rem;
  }
}
</style>