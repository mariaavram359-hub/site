<script setup>
const legi = [
  "Art.1 alin.2 - La efectuarea expertizelor criminalistice judiciare pot participa și experți criminaliști autorizați, numiți de organele judiciare la recomandarea părților.",
  "Art.7 alin.1 - Experții autorizați, numiți de organele judiciare, la cererea părților, participă personal la efectuarea expertizelor prin observații cu privire la obiectul expertizei, modificarea sau completarea acestuia, verificarea şi completarea materialului necesar pentru efectuarea expertizei, precum şi prin obiecții la raportul de expertiză, adresate organului judiciar.",
  "Art.7 alin.3 - Experții autorizați, numiți de organele judiciare, la cererea părților și recomandați de acestea, au dreptul să ia cunoștință de materialul dosarului necesar pentru efectuarea expertizei.",
  "Art.8 alin.1- Partea din proces care solicită să participe la efectuarea expertizei judiciare și un expert criminalist autorizat recomandat de ea va achita acestuia un onorariu stabilit de comun acord, adus la cunoștință, în scris, organului judiciar care numește expertul.",
  "Expertiza criminalistică ca act procesual este reglementată alături de celelalte tipuri de expertize prin Codul de procedură penală (art.172 – 181) și Codul de procedură civilă (art. 330-340)."
];
</script>

<template>
  <section id="legislatie" class="legislative-container">
    <div class="content">
      
      <h3 class="main-title">Cadru legislativ</h3>
      <p class="intro-text">
        Ordonanța Guvernului nr. 75/ 24.08.2000 privind organizarea activității de expertiză criminalistică reprezintă principalul act legislativ în domeniu, din cuprinsul căruia prezentăm în extras articolele ce conțin prevederi de interes pentru activitatea experților privați:
      </p>
      
      <div class="text-block">
        <ul class="clean-list law-list">
          <li v-for="(lege, idx) in legi" :key="'leg-'+idx">
            {{ lege }}
          </li>
        </ul>
      </div>

    </div>
  </section>
</template>

<style scoped>
.legislative-container {
  padding: 80px 20px;
  background-color: var(--bg-light); /* Un fundal ușor gri pentru a o separa de secțiunea anterioară */
}

.content {
  max-width: 900px;
  margin: 0 auto;
}

.main-title {
  font-size: 2rem;
  color: var(--primary-color);
  margin-bottom: 40px;
  text-align: left;
  border-bottom: 2px solid var(--accent-color); /* Linie roșie pentru accent */
  padding-bottom: 15px;
  line-height: 1.3;
}

.intro-text {
  font-size: 1.05rem;
  color: var(--text-dark);
  line-height: 1.6;
  margin-bottom: 25px;
  text-align: justify;
}

.text-block {
  margin-bottom: 30px;
  background: white;
  padding: 30px;
  border-radius: 4px;
  box-shadow: 0 4px 6px rgba(0,0,0,0.05);
}

.clean-list {
  list-style-type: none; /* Am scos punctele clasice aici pentru un aspect mai curat de paragrafe de lege */
  padding-left: 0;
  margin: 0;
}

.law-list li {
  margin-bottom: 20px;
  text-align: justify;
  font-size: 1.05rem;
  line-height: 1.6;
  color: var(--text-dark);
  padding-left: 15px;
  border-left: 3px solid var(--primary-color); /* O linie albastră discretă în stânga fiecărui articol */
}

.law-list li:last-child {
  margin-bottom: 0;
}

@media (max-width: 768px) {
  .main-title {
    font-size: 1.6rem;
  }
  .intro-text, .law-list li {
    text-align: left;
  }
  .text-block {
    padding: 20px 15px;
  }
}
</style>