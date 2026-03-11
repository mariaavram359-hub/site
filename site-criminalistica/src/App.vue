<script setup>
import SiteHeader from './components/SiteHeader.vue'
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'    
import ServicesSection from './components/ServicesSection.vue'
import ContactSection from './components/ContactSection.vue'
import DetailedServices from './components/DetailedServices.vue'
import LegislativeSection from './components/LegislativeSection.vue'

const numeExpert = "Avram Vasile-Adrian"; 
</script>

<template>
  <div class="app-container">
    <SiteHeader />
    <main>
      <HeroSection :nume="numeExpert" />
      <AboutSection />
      <ServicesSection />
      <DetailedServices />
      <LegislativeSection />
      <ContactSection />   
      
    </main>
    
    <footer style="text-align: center; padding: 20px; background: #142f52; color: white;">
      <p>&copy; 2026 Expert Criminalist {{ numeExpert }}</p>
    </footer>
  </div>
</template>

<style>
/* 1. Resetare și Variabile Globale */
:root {
  --primary-color: #0f172a; /* Albastru foarte închis (Navy) */
  --accent-color: #b91c1c;  /* Roșu închis (pentru butoane) */
  --text-dark: #334155;     /* Gri închis (pentru text) */
  --text-light: #f8fafc;    /* Aproape alb */
  --bg-light: #f1f5f9;      /* Gri foarte deschis (fundal secundar) */
  --font-main: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
}

/* 2. Reguli de bază */
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  padding: 0;
  font-family: var(--font-main);
  background-color: white;
  color: var(--text-dark);
  line-height: 1.6; /* Spațiu între rânduri pentru citire ușoară */
}

h1, h2, h3 {
  color: var(--primary-color);
  margin-top: 0;
}

ul {
  list-style: none;
  padding: 0;
}

a {
  text-decoration: none;
  color: inherit;
}

/* --- ADAPTĂRI PENTRU TELEFON (MOBILE RESPONSIVE) --- */
@media (max-width: 768px) {
  /* Micșorăm titlul uriaș de pe prima imagine */
  h1 {
    font-size: 2rem !important; 
  }
  
  /* Micșorăm titlurile secțiunilor (Despre, Servicii, etc.) */
  .section-title, h2, h3 {
    font-size: 1.6rem !important;
  }
  
  /* Reducem puțin spațiile goale (padding-ul) ca să nu pară pagina prea lungă pe mobil */
  .hero-wrapper, .about-container, .services-container, .contact-container {
    padding: 50px 15px !important;
  }
}
</style>