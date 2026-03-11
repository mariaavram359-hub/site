<script setup>
import pozaContact from '../assets/pozaCotact.jpg'
// Aici vei completa cu datele reale ale domnului Avram
const telefon = "0745779897"; 
const email = "expert@criminalist.ro"; 
const adresa = "Rm. Vâlcea, România"; 
</script>

<template>
  <section id="contact" class="contact-container">
    <div class="content">
      
      <h3 class="section-title">Contact</h3>
      
      <div class="contact-wrapper">
        
        <div class="contact-image">
          <img :src="pozaContact" alt="Avram Vasile-Adrian" />
        </div>
        
        <div class="contact-details">
          <p class="subtitle">
            Pentru programări, expertize și consultanță de specialitate, mă puteți contacta folosind datele de mai jos:
          </p>
          
          <div class="contact-box">
            <div class="contact-item">
              <span class="icon">📞</span>
              <div class="info-text">
                <strong>Telefon</strong>
                <a :href="'tel:' + telefon">{{ telefon }}</a>
              </div>
            </div>
            
            <div class="contact-item">
              <span class="icon">✉️</span>
              <div class="info-text">
                <strong>Email</strong>
                <a :href="'mailto:' + email">{{ email }}</a>
              </div>
            </div>
            
            <div class="contact-item">
              <span class="icon">📍</span>
              <div class="info-text">
                <span>{{ adresa }}</span>
              </div>
            </div>
          </div>
        </div>

      </div>

    </div>
  </section>
</template>

<style scoped>
.contact-container {
  padding: 80px 20px;
  background-color: white; 
}

.content {
  max-width: 1100px; /* Lățime suficientă pentru ambele coloane */
  margin: 0 auto;
}

.section-title {
  font-size: 2.5rem;
  color: var(--primary-color);
  margin-bottom: 50px;
  text-align: center;
  position: relative;
}

.section-title::after {
  content: '';
  display: block;
  width: 60px;
  height: 4px;
  background: var(--accent-color);
  margin: 15px auto 0;
}

/* Structura pe 2 coloane */
.contact-wrapper {
  display: flex;
  gap: 50px; /* Spațiul dintre poză și text */
  align-items: center; /* Le centrează perfect pe verticală */
}

/* Stilizarea fotografiei (Stânga) */
.contact-image {
  flex: 1; /* Ocupă jumătate din spațiu */
}

.contact-image img {
  width: 100%;
  height: auto;
  border-radius: 8px;
  box-shadow: 0 10px 20px rgba(0,0,0,0.1);
  border-left: 5px solid var(--primary-color); /* Un detaliu subtil care leagă designul de restul site-ului */
  object-fit: cover;
}

/* Stilizarea textului (Dreapta) */
.contact-details {
  flex: 1; /* Ocupă cealaltă jumătate */
}

.subtitle {
  font-weight: bold;
  color: #000000;
  font-size: 1.5rem;
  margin-bottom: 30px;
  line-height: 1.6;
}

.contact-box {
  display: flex;
  flex-direction: column;
  gap: 25px;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 20px;
  background: var(--bg-light);
  padding: 20px 25px;
  border-radius: 6px;
  border-left: 4px solid var(--accent-color);
  transition: transform 0.2s ease;
}

.contact-item:hover {
  transform: translateX(10px);
}

.icon {
  font-size: 1.8rem;
}

.info-text {
  display: flex;
  flex-direction: column;
}

.info-text strong {
  color: var(--text-dark);
  font-size: 0.9rem;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  margin-bottom: 3px;
}

.info-text a, .info-text span {
  color: var(--primary-color);
  font-size: 1.2rem;
  font-weight: bold;
  text-decoration: none;
  transition: color 0.3s;
}

.info-text a:hover {
  color: var(--accent-color);
}

/* Adaptare automată pentru telefoane și tablete (coloanele se așază una sub alta) */
@media (max-width: 900px) {
  .contact-wrapper {
    flex-direction: column;
  }
  .contact-image {
    width: 100%;
    max-width: 500px; /* Să nu se facă uriașă pe tablete */
    margin: 0 auto;
    flex: 0 0 20%;
  }
  .contact-details {
    width: 100%;
    text-align: center;
    flex: 1;
  }
  .contact-item {
    justify-content: center;
    text-align: left;
  }
}
</style>