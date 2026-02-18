<script setup>
import { ref } from 'vue'

const formData = ref({
  nom: '',
  email: '',
  sujet: '',
  message: ''
})

const envoyerMessage = () => {
  // Ici vous pouvez ajouter la logique d'envoi du message
  alert('Message envoyé ! Je vous répondrai dans les plus brefs délais.')
  // Réinitialiser le formulaire
  formData.value = { nom: '', email: '', sujet: '', message: '' }
}
</script>

<template>
  <div class="contact">
    <div class="container">
      <h1 class="page-title">Contactez-moi</h1>
      
      <div class="contact-content">
        <!-- Informations de contact -->
        <div class="contact-info">
          <h2>Restons en contact</h2>
          <p>N'hésitez pas à me contacter pour toute opportunité professionnelle ou collaboration.</p>
          
          <div class="info-items">
            <div class="info-item">
              <span class="icon">📧</span>
              <div>
                <h3>Email</h3>
                <p>njetchounzepadaniel@gmail.com</p>
                <p>daniel.njetchou@2028.ucac-icam.com</p>
              </div>
            </div>
            
            <div class="info-item">
              <span class="icon">📱</span>
              <div>
                <h3>Téléphone</h3>
                <p>+237 698835795</p>
              </div>
            </div>
            
            <div class="info-item">
              <span class="icon">📍</span>
              <div>
                <h3>Adresse</h3>
                <p>Yassa, Douala - Cameroun</p>
              </div>
            </div>
            
            <div class="info-item">
              <span class="icon">🔗</span>
              <div>
                <h3>TryHackMe</h3>
                <p>SOC Level 1 (en cours)</p>
              </div>
            </div>
          </div>

          <!-- Réseaux sociaux -->
          <div class="social-links">
            <a href="#" class="https://www.linkedin.com/in/daniel-jordan-njetchou-nzepa-6a057733b?utm_source=share_via&utm_content=profile&utm_medium=member_ios">LinkedIn</a>
            <a href="#" class="https://github.com/nnd-gb">GitHub</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.contact {
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

.contact-content {
  display: inline;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
}

.contact-info, .contact-form {
  background: white;
  padding: 2rem;
  border-radius: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.contact-info h2, .contact-form h2 {
  color: #333;
  margin-bottom: 1.5rem;
  font-size: 1.5rem;
}

.contact-info > p {
  color: #666;
  line-height: 1.6;
  margin-bottom: 2rem;
}

.info-items {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  margin-bottom: 2rem;
}

.info-item {
  display: flex;
  gap: 1rem;
  align-items: flex-start;
}

.info-item .icon {
  font-size: 1.5rem;
  min-width: 2rem;
}

.info-item h3 {
  color: #333;
  font-size: 1rem;
  margin-bottom: 0.25rem;
}

.info-item p {
  color: #666;
  line-height: 1.4;
}

.social-links {
  display: flex;
  gap: 1rem;
}

.social-link {
  color: #667eea;
  text-decoration: none;
  padding: 0.5rem 1rem;
  border: 1px solid #667eea;
  border-radius: 25px;
  transition: all 0.3s;
}

.social-link:hover {
  background: #667eea;
  color: white;
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-group label {
  display: block;
  margin-bottom: 0.5rem;
  color: #333;
  font-weight: 500;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 0.75rem;
  border: 1px solid #ddd;
  border-radius: 5px;
  font-size: 1rem;
  transition: border-color 0.3s;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #667eea;
}

.submit-btn {
  width: 100%;
  padding: 1rem;
  background: #667eea;
  color: white;
  border: none;
  border-radius: 5px;
  font-size: 1rem;
  font-weight: bold;
  cursor: pointer;
  transition: background 0.3s;
}

.submit-btn:hover {
  background: #5a67d8;
}

@media (max-width: 768px) {
  .contact-content {
    grid-template-columns: 1fr;
  }
}

/* Dans ContactView.vue */

@media screen and (max-width: 768px) {
  .contact {
    padding: 2rem 1rem;
  }

  .page-title {
    font-size: 2rem;
    margin-bottom: 2rem;
  }

  .contact-content {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }

  .contact-info, .contact-form {
    padding: 1.5rem;
  }

  .contact-info h2, .contact-form h2 {
    font-size: 1.3rem;
  }

  .info-item {
    flex-direction: column;
    align-items: flex-start;
    gap: 0.5rem;
  }

  .info-item .icon {
    font-size: 1.3rem;
  }

  .social-links {
    flex-wrap: wrap;
    justify-content: center;
  }

  .social-link {
    padding: 0.4rem 0.8rem;
    font-size: 0.9rem;
  }

  .form-group input,
  .form-group textarea {
    padding: 0.6rem;
    font-size: 0.95rem;
  }

  .submit-btn {
    padding: 0.8rem;
    font-size: 0.95rem;
  }
}

@media screen and (max-width: 480px) {
  .page-title {
    font-size: 1.8rem;
  }

  .contact-info, .contact-form {
    padding: 1rem;
  }

  .info-item {
    gap: 0.25rem;
  }

  .info-item h3 {
    font-size: 0.95rem;
  }

  .info-item p {
    font-size: 0.9rem;
    word-break: break-word;
  }

  .social-link {
    width: 100%;
    text-align: center;
  }
}

/* Pour très petits écrans */
@media screen and (max-width: 320px) {
  .contact-info h2, .contact-form h2 {
    font-size: 1.1rem;
  }

  .form-group label {
    font-size: 0.9rem;
  }

  .form-group input,
  .form-group textarea {
    font-size: 0.9rem;
  }
}

</style>