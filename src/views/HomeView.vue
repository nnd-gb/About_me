<script setup>
import { ref } from 'vue'
import ProjectCard from '../components/ProjectCard.vue'

const projects = ref([
  {
    title: "Infrastructure réseau sécurisée",
    description: "Conception d'une infrastructure réseau avec 6 sites interconnectés sur Cisco Packet Tracer",
    technologies: ["OSPF", "RIP", "EtherChannel", "DNS"],
    image: "network-project.jpg" // Vous pouvez ajouter une image plus tard
  },
  {
    title: "Site Web Full Stack",
    description: "Développement complet d'un site web avec React.js, Laravel et PostgreSQL",
    technologies: ["React.js", "Laravel", "PostgreSQL"],
    image: "web-project.jpg"
  },
  {
    title: "Infrastructure SOC",
    description: "Mise en place d'une infrastructure SOC avec Wazuh, Shuffle, Grafana et OpenVAS",
    technologies: ["Wazuh", "Shuffle", "Grafana", "OpenVAS"],
    image: "soc-project.jpg"
  }
])
</script>

<template>
  <main class="home">
    <!-- Hero Section -->
    <section class="hero">
      <div class="hero-content">
        <img src="../assets/logo.png" alt="Logo" class="logo" />
        <h1>NJETCHOU NZEPA DANIEL JORDAN</h1>
        <h2>Étudiant en 3ème année en Génie Informatique</h2>
        <p class="subtitle">Passionné par la cybersécurité et le développement web</p>
        <div class="hero-buttons">
          <router-link to="/about" class="btn primary">En savoir plus</router-link>
          <a href="https://drive.google.com/uc?export=download&id=1jXd34OM5SNcjfzLBpcSgkIEQONp0WnQz" class="btn secondary" target="_blank">
            Télécharger mon CV
          </a>
        </div>
      </div>
    </section>

    <!-- Projets Section -->
    <section class="projects">
      <h2 class="section-title">Mes Projets Récents</h2>
      <div class="projects-grid">
        <ProjectCard
          v-for="(project, index) in projects"
          :key="index"
          :project="project"
        />
      </div>
    </section>

    <!-- Compétences rapides -->
    <section class="skills-preview">
      <h2 class="section-title">Compétences Clés</h2>
      <div class="skills-cloud">
        <span class="skill-tag">Wireshark</span>
        <span class="skill-tag">React.js</span>
        <span class="skill-tag">Vue.js</span>
        <span class="skill-tag">Next.js</span>
        <span class="skill-tag">PostgreSQL</span>
        <span class="skill-tag">Laravel</span>
        <span class="skill-tag">CCNA 1</span>
        <span class="skill-tag">Kali Linux</span>
        <span class="skill-tag">Proxmox</span>
        <span class="skill-tag">Wazuh</span>
      </div>
    </section>
  </main>
</template>

<style scoped>
.home {
  min-height: 100vh;
}

.hero {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  padding: 4rem 2rem;
  text-align: center;
}

.hero-content {
  max-width: 800px;
  margin: 0 auto;
}

.logo {
  width: 120px;
  height: 120px;
  margin-bottom: 2rem;
  border-radius: 50%;
  border: 4px solid white;
}

.hero h1 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.hero h2 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
  opacity: 0.9;
}

.subtitle {
  font-size: 1.2rem;
  margin-bottom: 2rem;
  opacity: 0.8;
}

.hero-buttons {
  display: flex;
  gap: 1rem;
  justify-content: center;
}

.btn {
  padding: 1rem 2rem;
  border-radius: 50px;
  text-decoration: none;
  font-weight: bold;
  transition: transform 0.3s;
}

.btn:hover {
  transform: translateY(-2px);
}

.btn.primary {
  background: white;
  color: #667eea;
}

.btn.secondary {
  background: transparent;
  color: white;
  border: 2px solid white;
}

.projects, .skills-preview {
  padding: 4rem 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.section-title {
  text-align: center;
  font-size: 2rem;
  color: #333;
  margin-bottom: 3rem;
  position: relative;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 60px;
  height: 3px;
  background: #667eea;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.skills-cloud {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  justify-content: center;
}

.skill-tag {
  background: #f0f0f0;
  padding: 0.5rem 1rem;
  border-radius: 25px;
  font-size: 0.9rem;
  color: #555;
  transition: all 0.3s;
}

.skill-tag:hover {
  background: #667eea;
  color: white;
  transform: scale(1.05);
}

@media (max-width: 768px) {
  .hero h1 {
    font-size: 2rem;
  }
  
  .hero-buttons {
    flex-direction: column;
  }
}
</style>