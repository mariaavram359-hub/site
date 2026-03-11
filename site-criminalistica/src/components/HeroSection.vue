<script setup>
// Am pus specializările într-o listă (array) ca să fie ușor de stilizat și modificat pe viitor
const specializari = [
  "EXPERTIZA GRAFICĂ ȘI TEHNICĂ A DOCUMENTELOR",
  "EXPERTIZA DACTILOSCOPICĂ A URMELOR PALMARE ȘI PLANTARE",
  "EXPERTIZA BALISTCĂ A ARMELOR ȘI MUNIȚIILOR"
];
</script>

<template>
  <section id="acasa" class="hero-wrapper">
    <div class="content">
      
      <h1>AVRAM VASILE-ADRIAN</h1>
      <h2>Expert criminalist autorizat în specialitățile:</h2>
      
      <ul class="specializations-list">
        <li v-for="(item, index) in specializari" :key="index">
          {{ item }}
        </li>
      </ul>

    </div>
  </section>
</template>

<style scoped>
.hero-wrapper {
  /* NOU: Albastru mai deschis în gradient (overlay) */
  background: linear-gradient(rgba(30, 60, 150, 0.85), rgba(30, 60, 150, 0.8)), 
              url('https://images.unsplash.com/photo-1450101499163-c8848c66ca85?auto=format&fit=crop&w=1920&q=80');
  background-size: cover;
  background-position: center;
  padding: 120px 20px;
  text-align: center;
  min-height: 75vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
.content {
  max-width: 900px;
  width: 100%;
  background: rgba(0, 0, 0, 0.4);
  padding: 50px;
  border-radius: 8px;
  backdrop-filter: blur(4px);
  border-top: 4px solid var(--accent-color); /* O linie roșie sus pentru eleganță */
}

h1 {
  color: white;
  font-size: 3.5rem;
  margin-bottom: 10px;
  letter-spacing: 2px;
}

h2 {
  color: #cbd5e1; /* Gri deschis */
  font-size: 1.4rem;
  font-weight: 300;
  margin-bottom: 40px;
  text-transform: uppercase;
  letter-spacing: 1px;
}

/* Stilizarea listei de specializări */
.specializations-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 15px; /* Spațiu între rânduri */
}

.specializations-list li {
  color: white;
  font-size: 1.15rem;
  font-weight: 500;
  letter-spacing: 1px;
  background: rgba(255, 255, 255, 0.08); /* Un fundal ușor transparent */
  padding: 15px 20px;
  border-radius: 4px;
  border-left: 4px solid var(--accent-color); /* Linie de accent în stânga fiecărui rând */
  transition: transform 0.3s ease, background 0.3s ease;
}

/* Efect discret la trecerea mouse-ului */
.specializations-list li:hover {
  transform: translateX(10px);
  background: rgba(255, 255, 255, 0.15);
}

/* Adaptare pentru telefoane mobile */
@media (max-width: 768px) {
  h1 { font-size: 2.2rem !important; }
  h2 { font-size: 1.1rem !important; margin-bottom: 25px; }
  .specializations-list li { font-size: 0.95rem; padding: 12px; }
  .content { padding: 30px 15px; }
}
</style>