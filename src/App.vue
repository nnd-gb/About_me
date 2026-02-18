<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div id="app">
    <!-- Header avec menu responsive -->
    <header>
      <nav class="navbar">
        <div class="nav-container">
          <router-link to="/" class="logo">
            <img src="./assets/logo.png" alt="Logo" class="nav-logo" />
            <span class="logo-text">NJETCHOU N.D.J.</span>
          </router-link>
          
          <!-- Menu burger pour mobile -->
          <button class="burger-menu" @click="toggleMenu" :class="{ active: isMenuOpen }">
            <span></span>
            <span></span>
            <span></span>
          </button>

          <!-- Navigation -->
          <ul class="nav-menu" :class="{ active: isMenuOpen }">
            <li><router-link to="/" class="nav-link" @click="closeMenu">Accueil</router-link></li>
            <li><router-link to="/about" class="nav-link" @click="closeMenu">À propos</router-link></li>
            <li><router-link to="/contact" class="nav-link" @click="closeMenu">Contact</router-link></li>
          </ul>
        </div>
      </nav>
    </header>

    <main>
      <RouterView />
    </main>

    <footer class="footer">
      <div class="footer-content">
        <p>&copy; 2026 NJETCHOU NZEPA Daniel Jordan</p>
        <div class="footer-links">
          <a href="https://github.com/nnd-gb" target="_blank">GitHub</a>
          <a href="https://www.linkedin.com/in/daniel-jordan-njetchou-nzepa-6a057733b?utm_source=share_via&utm_content=profile&utm_medium=member_ios" target="_blank">LinkedIn</a>
          <a href="https://tryhackme.com/p/daniel.gb" target="_blank">TryHackMe</a>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isMenuOpen: false
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen
      // Empêcher le scroll quand le menu est ouvert
      if (this.isMenuOpen) {
        document.body.style.overflow = 'hidden'
      } else {
        document.body.style.overflow = 'auto'
      }
    },
    closeMenu() {
      this.isMenuOpen = false
      document.body.style.overflow = 'auto'
    }
  }
}
</script>

<style>
/* Reset et styles de base */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
  line-height: 1.6;
  color: #333;
  overflow-x: hidden;
  width: 100%;
}

#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  width: 100%;
  overflow-x: hidden;
}

/* Header & Navigation */
.navbar {
  background: white;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  position: sticky;
  top: 0;
  z-index: 1000;
  width: 100%;
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: relative;
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  text-decoration: none;
  font-size: 1.5rem;
  font-weight: bold;
  color: #667eea;
  z-index: 1001;
}

.nav-logo {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  object-fit: cover;
}

/* Menu Burger */
.burger-menu {
  display: none;
  flex-direction: column;
  justify-content: space-around;
  width: 30px;
  height: 30px;
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 0;
  z-index: 1001;
}

.burger-menu span {
  width: 30px;
  height: 3px;
  background: #333;
  border-radius: 10px;
  transition: all 0.3s linear;
  position: relative;
  transform-origin: 1px;
}

.burger-menu.active span:first-child {
  transform: rotate(45deg);
}

.burger-menu.active span:nth-child(2) {
  opacity: 0;
}

.burger-menu.active span:last-child {
  transform: rotate(-45deg);
}

/* Menu de navigation */
.nav-menu {
  display: flex;
  list-style: none;
  gap: 2rem;
  margin: 0;
  padding: 0;
  transition: all 0.3s ease;
}

.nav-link {
  text-decoration: none;
  color: #333;
  font-weight: 500;
  transition: color 0.3s;
  padding: 0.5rem 1rem;
  border-radius: 5px;
  font-size: 1rem;
}

.nav-link:hover {
  color: #667eea;
  background: #f5f5f5;
}

.nav-link.router-link-exact-active {
  color: #667eea;
  background: #f0f0f0;
}

/* Main content */
main {
  flex: 1;
  width: 100%;
  max-width: 100%;
  overflow-x: hidden;
}

/* Footer */
.footer {
  background: #2c3e50;
  color: white;
  margin-top: auto;
  width: 100%;
}

.footer-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem 1rem;
  text-align: center;
}

.footer-links {
  margin-top: 1rem;
  display: flex;
  gap: 1.5rem;
  justify-content: center;
  flex-wrap: wrap;
}

.footer-links a {
  color: white;
  text-decoration: none;
  opacity: 0.8;
  transition: opacity 0.3s;
  font-size: 0.9rem;
}

.footer-links a:hover {
  opacity: 1;
}

/* ========== MEDIA QUERIES ========== */

/* Tablettes (768px et moins) */
@media screen and (max-width: 768px) {
  .burger-menu {
    display: flex;
  }

  .nav-menu {
    position: fixed;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100vh;
    background: white;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 2rem;
    transition: left 0.3s ease;
    z-index: 1000;
  }

  .nav-menu.active {
    left: 0;
  }

  .nav-link {
    font-size: 1.2rem;
    padding: 1rem 2rem;
    width: 200px;
    text-align: center;
  }

  .nav-link:hover {
    background: #667eea;
    color: white;
  }

  .logo-text {
    font-size: 1.2rem;
  }

  .nav-logo {
    width: 35px;
    height: 35px;
  }
}

/* Petits mobiles (480px et moins) */
@media screen and (max-width: 480px) {
  .nav-container {
    padding: 0.8rem;
  }

  .logo {
    font-size: 1.2rem;
  }

  .nav-logo {
    width: 30px;
    height: 30px;
  }

  .footer-content {
    padding: 1.5rem 1rem;
  }

  .footer-links {
    gap: 1rem;
    flex-direction: column;
    align-items: center;
  }

  .footer-links a {
    display: block;
    padding: 0.3rem;
  }
}

/* Très petits mobiles (320px) */
@media screen and (max-width: 320px) {
  .logo-text {
    display: none; /* Cache le texte du logo sur très petits écrans */
  }

  .nav-logo {
    width: 35px;
    height: 35px;
  }

  .nav-link {
    font-size: 1rem;
    padding: 0.8rem 1.5rem;
    width: 180px;
  }
}

/* Pour les écrans en orientation paysage sur mobile */
@media screen and (max-height: 500px) and (orientation: landscape) {
  .nav-menu {
    padding: 2rem 0;
    overflow-y: auto;
  }

  .nav-link {
    padding: 0.5rem 1rem;
    margin: 0.2rem 0;
  }
}

/* Support des écrans haute résolution */
@media (-webkit-min-device-pixel-ratio: 2), (min-resolution: 192dpi) {
  .nav-logo {
    image-rendering: -webkit-optimize-contrast;
  }
}

/* Améliorations pour le tactile */
@media (hover: none) and (pointer: coarse) {
  .nav-link {
    padding: 0.8rem 1.2rem; /* Plus grand pour le tactile */
  }

  .burger-menu span {
    height: 4px; /* Plus épais pour le tactile */
  }
}
</style>