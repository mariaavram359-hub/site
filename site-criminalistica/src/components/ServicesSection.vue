<script setup>
// Datele tale introduse exact cum le-ai scris
const servicii = [
  {
    titlu: "Consultanță",
    descriere: "Presupune oferirea de informații cu caracter general privitor la posibilitățile de lucru și serviciile ce pot fi oferite, analiza speței prezentate și a examinărilor solicitate, studierea preliminară a documentelor, probelor, etc., urmate de recomandările expertului cu privire la activitățile care pot fi desfășurate în funcție de complexitatea cazului."
  },
  {
    titlu: "Reprezentarea clientului",
    descriere: "Ca expert parte, cu ocazia stabilirii obiectivelor expertizei criminalistice judiciare precum și în urma întocmirii raportului de expertiză judiciară și a formulării concluziilor acestuia, în conformitate cu art. 7, alin. 1 din Ordonanța Guvernului nr. 75/2000."
  },
  {
    titlu: "Efectuarea de Expertize Criminalistice extrajudiciare",
    descriere: "Expertiza criminalistică extrajudiciară poate fi solicitată și utilizată ca probă în cadrul unui proces penal ori civil, dar și în afara acestuia, ca răspuns ce poate orienta beneficiarul în demersurile sale sau strategia pe care o poate adopta în cauza sa. De asemenea, expertiza criminalistică extrajudiciară efectuată ulterior unei expertize criminalistice oficiale poate lămuri anumite presupuneri sau îndoieli ale beneficiarului cu privire la concluziile expertizei criminalistice oficiale."
  }
];
</script>

<template>
  <section id="servicii" class="services-container">
    <div class="content">
      
      <h3 class="section-title">Servicii Oferite</h3>
      
      <div class="services-grid">
        <div v-for="(serviciu, index) in servicii" :key="index" class="service-card">
          <h4>{{ serviciu.titlu }}</h4>
          <p>{{ serviciu.descriere }}</p>
        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
.services-container {
  padding: 80px 20px;
  background-color: var(--bg-light); /* Un fundal ușor diferit pentru a separa vizual de secțiunea "Despre" */
}

.content {
  max-width: 1200px;
  margin: 0 auto;
}

.section-title {
  color: var(--primary-color);
  font-size: 2.5rem;
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

.services-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
}

/* Designul chenarelor de servicii */
.service-card {
  background: white;
  padding: 40px 30px;
  border-radius: 4px;
  border-top: 5px solid var(--accent-color); /* Folosim linia roșie de accent aici pentru a diferenția de chenarele albastre de sus */
  box-shadow: 0 4px 10px rgba(0,0,0,0.04);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  display: flex;
  flex-direction: column;
}

.service-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0,0,0,0.08);
}

.service-card h4 {
  margin-top: 0;
  margin-bottom: 20px;
  color: var(--primary-color);
  font-size: 1.3rem;
  text-align: center;
  border-bottom: 1px solid #e2e8f0;
  padding-bottom: 15px;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.service-card p {
  color: var(--text-dark);
  line-height: 1.6;
  font-size: 1rem;
  text-align: justify;
  margin: 0;
}

/* Adaptare pentru tablete și telefoane */
@media (max-width: 992px) {
  .services-grid {
    grid-template-columns: 1fr; /* Trece la o singură coloană pe ecrane mici */
  }
  .service-card p {
    text-align: left;
  }
}


</style>