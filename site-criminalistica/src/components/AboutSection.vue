<script setup>
const informatiiDespre = [
  {
    titlu: "Autorizare",
    paragrafe: [
      "Expert criminalist autorizat în specialitățile menționate, cu brevete obținute în baza activității desfășurate în cadrul Serviciului Criminalistic din I.P.J. Vâlcea și a examenelor susținute în cadrul Institutului Național de Criminalistică al Poliției Române.",
      "Înscris, potrivit prevederilor Ordonanței Guvernului nr. 75/2000 privind organizarea activității de expertiză criminalistică, aprobată cu modificări și completări prin Legea nr. 488/2002, modificată și completată prin Legea nr. 156/2011, în ”Tabelul nominal cu experții criminaliști autorizați”, întocmit de Ministerul Justiției și publicat în Monitorul Oficial nr. 4261 /12.10. 2024, partea a IV-a, la pozițiile: 290 pentru expertiza grafică și tehnică a documentelor, 314 pentru expertiza dactiloscopică a urmelor palmare și plantare și 217 pentru expertiza balistică a armelor și munițiilor;"
    ]
  },
  {
    titlu: "Experiență Profesională",
    paragrafe: [
      "Experiență de 30 de ani în Ministerul de Interne, dintre care 28 de ani în cadrul Serviciului Criminalistic al Inspectoratului de Poliție Județean Vâlcea, perioadă în care am participat la investigarea tehnico-științifică a locului faptei și am efectuat constatări și expertize criminalistice în calitate de specialist sau expert criminalist, într-un număr semnificativ de cauze.",
      "Șeful Biroului de Investigare Tehnico-Științifică a Locului Faptei din cadrul Serviciului Criminalistic al Inspectoratului de Poliție Județean Vâlcea în perioada 2016-2023."
    ]
  },
  {
    titlu: "Studii și Pregătire",
    paragrafe: [
      "Licențiat în științe juridice, absolvent al Academiei de Poliție „Alexandru Ioan Cuza” din București - Facultatea de drept, profilul Științe juridice, specializarea Drept.",
      "Pregătire continuă realizată prin stagii și cursuri de perfecționare privind expertizele și constatările criminalistice, managementul cercetării la fața locului, managementul calității în laboratoarele criminalistice, organizate de Institutului Național de Criminalistică."
    ]
  }
];
</script>

<template>
  <section id="despre" class="about-container">
    <div class="content">
      
      <h3 class="section-title">Despre Expert</h3>
      
      <div class="columns-layout">
        <div v-for="(info, index) in informatiiDespre" :key="index" class="column-box">
          <div class="box-header">
            <h4>{{ info.titlu }}</h4>
          </div>
          <div class="box-content">
            <p v-for="(paragraf, idx) in info.paragrafe" :key="idx">
              {{ paragraf }}
            </p>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
.about-container {
  padding: 80px 20px;
  background-color: white; 
}

.content {
  max-width: 1200px; /* Am lățit zona pentru a încăpea frumos 3 coloane */
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

/* Grila cu 3 coloane egale */
.columns-layout {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* Împarte spațiul în 3 fracții egale */
  gap: 30px; /* Spațiu între coloane */
}

/* Stilizarea chenarelor formale */
.column-box {
  background-color: var(--bg-light);
  padding: 35px 25px;
  border-radius: 4px;
  border-top: 5px solid var(--primary-color); /* Linia de autoritate o mutăm sus pentru formatul coloană */
  box-shadow: 0 4px 6px rgba(0,0,0,0.05);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  display: flex;
  flex-direction: column; /* Asigură că textul se întinde frumos pe verticală în interiorul cutiei */
}

.column-box:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 15px rgba(0,0,0,0.08);
}

.box-header {
  margin-bottom: 20px;
  border-bottom: 1px solid #cbd5e1;
  padding-bottom: 15px;
}

.column-box h4 {
  margin: 0;
  color: var(--primary-color);
  font-size: 1.3rem;
  text-align: center;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.box-content p {
  color: var(--text-dark);
  font-size: 1rem;
  line-height: 1.6;
  margin-bottom: 15px;
  text-align: justify;
}

.box-content p:last-child {
  margin-bottom: 0;
}

/* Adaptare pentru tablete și telefoane (trecem la 1 coloană) */
@media (max-width: 992px) {
  .columns-layout {
    grid-template-columns: 1fr; /* Le așază una sub alta când nu mai e spațiu orizontal */
  }
  .box-content p {
    text-align: left; /* Eliminăm textul justify pe ecrane mici */
  }
}
</style>