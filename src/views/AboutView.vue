<script setup>
import { ref } from 'vue'

const cvDriveLink = '/CV_NJETCHOU_NZEPA_DANIEL_2026.pdf' // À remplacer par votre vrai lien
</script>

<template>
  <div class="about">
    <div class="container">
      <h1 class="page-title">À propos de moi</h1>
      
      <div class="about-content">
        <!-- Colonne gauche : CV visuel -->
        <div class="cv-section">
          <h2>Mon CV</h2>
          <div class="cv-visual-container">
            <img 
              src="../assets/cv-visual.png" 
              alt="Visualisation du CV" 
              class="cv-visual"
            />
            <div class="cv-overlay">
              <a :href="cvDriveLink" target="_blank" class="download-btn">
                <span class="icon">📄</span>
                Télécharger CV (PDF)
              </a>
            </div>
          </div>
        </div>

        <!-- Colonne droite : Bio détaillée -->
        <div class="bio-section">
          <h2>Qui suis-je ?</h2>
          <p class="bio-text">
            Je suis un étudiant en 3ème année de Génie Informatique à l'Institut Ucac-Icam, 
            passionné par la cybersécurité et le développement web aspirant à faire dans le domaine de la cybersécurité. Mon parcours m'a permis 
            d'acquérir des compétences solides aussi bien en développement d'applications 
            qu'en sécurité informatique.
          </p>

          <h3>Formation</h3>
          <ul class="education-list">
            <li>
              <strong>Institut Ucac-Icam</strong> - Génie Informatique (2023-en cours)
            </li>
            <li>
              <strong>College Libermann</strong> - Baccalauréat D
            </li>
          </ul>

          <h3>Certifications</h3>
          <ul class="cert-list">
            <li>CCNA 1 - Cisco</li>
            <li>TryHackMe - SOC Level 1 (en cours)</li>
          </ul>

          <h3>Expériences professionnelles</h3>
          
          <div class="experience">
            <h4>Prise en main et configuration d'un SIEM</h4>
            <p class="company">Stage en entreprise</p>
            <p>Installation et configuration de Wazuh (SIEM/XDR) pour la collecte et la surveillance des logs, facilitant la détection des pannes et bugs réseau.</p>
          </div>

          <div class="experience">
            <h4>Système de détection et réponse aux incidents</h4>
            <p class="company">ITGStore</p>
            <p>Collaboration avec l'équipe cybersécurité pour mettre en place une infrastructure SOC intégrant Wazuh, Shuffle, Grafana et OpenVAS.</p>
          </div>

          <h3>Langues</h3>
          <ul class="languages">
            <li>Français - Langue maternelle</li>
            <li>Anglais - Niveau intermédiaire</li>
          </ul>

          <h3>Centres d'intérêt</h3>
          <ul class="interests">
            <li>📚 Lecture</li>
            <li>🎬 Anime</li>
            <li>🎮 Jeux vidéos</li>
            <li>🔐 Cybersécurité (TryHackMe)</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.about {
  background: #f5f5f5;
  min-height: 100vh;
  padding: 4rem 2rem;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.page-title {
  text-align: center;
  font-size: 2.5rem;
  color: #333;
  margin-bottom: 3rem;
  position: relative;
}

.page-title::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 80px;
  height: 4px;
  background: #667eea;
}

.about-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
}

.cv-section h2, .bio-section h2 {
  color: #333;
  margin-bottom: 1.5rem;
}

.cv-visual-container {
  position: relative;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}

.cv-visual {
  width: 100%;
  height: auto;
  display: block;
  transition: transform 0.3s;
}

.cv-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(102, 126, 234, 0.9);
  display: flex;
  justify-content: center;
  align-items: center;
  opacity: 0;
  transition: opacity 0.3s;
}

.cv-visual-container:hover .cv-overlay {
  opacity: 1;
}

.cv-visual-container:hover .cv-visual {
  transform: scale(1.05);
}

.download-btn {
  background: white;
  color: #667eea;
  padding: 1rem 2rem;
  border-radius: 50px;
  text-decoration: none;
  font-weight: bold;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  transition: transform 0.3s;
}

.download-btn:hover {
  transform: translateY(-2px);
}

.icon {
  font-size: 1.2rem;
}

.bio-text {
  color: #666;
  line-height: 1.8;
  margin-bottom: 2rem;
}

.bio-section h3 {
  color: #333;
  margin: 2rem 0 1rem;
  font-size: 1.3rem;
}

.education-list, .cert-list, .languages, .interests {
  list-style: none;
  padding: 0;
}

.education-list li, .cert-list li, .languages li, .interests li {
  padding: 0.5rem 0;
  border-bottom: 1px solid #eee;
  color: #666;
}

.experience {
  background: white;
  padding: 1.5rem;
  border-radius: 8px;
  margin-bottom: 1rem;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.experience h4 {
  color: #333;
  margin-bottom: 0.25rem;
}

.experience .company {
  color: #667eea;
  font-size: 0.9rem;
  margin-bottom: 0.5rem;
}

.experience p {
  color: #666;
  line-height: 1.6;
}

@media (max-width: 768px) {
  .about-content {
    grid-template-columns: 1fr;
  }
}


@media screen and (max-width: 768px) {
  .about {
    padding: 2rem 1rem;
  }

  .page-title {
    font-size: 2rem;
    margin-bottom: 2rem;
  }

  .about-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .cv-section, .bio-section {
    padding: 1rem;
  }

  .cv-section h2, .bio-section h2 {
    font-size: 1.3rem;
  }

  .bio-text {
    font-size: 0.95rem;
  }

  .experience {
    padding: 1rem;
  }

  .download-btn {
    padding: 0.8rem 1.5rem;
    font-size: 0.9rem;
  }
}

@media screen and (max-width: 480px) {
  .page-title {
    font-size: 1.8rem;
  }

  .experience h4 {
    font-size: 1rem;
  }

  .company {
    font-size: 0.85rem;
  }
}

</style>