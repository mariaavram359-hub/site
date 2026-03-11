<script setup>
const expertize = [
  {
    titlu: "EXPERTIZA GRAFICĂ ȘI TEHNICĂ A DOCUMENTELOR",
    intrebari: [
      "dacă scrisul în litigiu a fost executat de una sau mai multe persoane;",
      "dacă scrisul în litigiu a fost executat de persoana pentru care este pus la dispoziție scrisul de comparație;",
      "dacă documentul în litigiu prezintă modificări, adăugiri, ștersături;",
      "stabilirea textului acoperit;",
      "dacă două sau mai multe semnături în litigiu au fost realizate de către o singură persoană;",
      "dacă semnătura în litigiu a fost executată de către titular sau altă persoană;",
      "dacă scrisul ori semnătura în litigiu au fost realizate cu instrument scriptural, direct (ex. cerneală, pastă de pix etc.) sau indirect (ex. hârtie copiativă, indigo etc.) ori prin alte procedee (ex. mijloace electronice, colaj etc.);",
      "dacă substanța scripturală cu care este realizat scrisul și/sau semnătura în litigiu este diferită de cea cu care este realizat scrisul și/sau semnătura model de comparație;",
      "dacă textul dactilografiat în litigiu a fost realizat sau nu cu o singură mașină de scris sau dacă a fost realizat cu ajutorul mașinii de scris puse la dispoziție;",
      "dacă documentele supuse examinării au fost sau nu realizate cu ajutorul aceleiași imprimante sau cu ajutorul imprimantei puse la dispoziție;",
      "dacă documentele de identitate în litigiu ori alte documente ce prezintă elemente de siguranță sunt autentice, contrafăcute sau falsificate;",
      "dacă impresiunile de ștampilă în litigiu au fost aplicate cu ștampilele puse la dispoziție ori dacă sunt realizate prin ștampilare sau prin alte procedee;"
    ]
  },
  {
    titlu: "EXPERTIZA DACTILOSCOPICĂ A URMELOR PALMARE ȘI PLANTARE",
    intrebari: [
      "dacă pe obiectul pus la dispoziție se evidențiază urme papilare;",
      "dacă urmele papilare evidențiate conțin suficiente detalii dactiloscopice macroscopice calitative si cantitative necesare efectuării comparațiilor dactiloscopice;",
      "dacă urmele papilare evidențiate sau puse la dispoziție au fost create de persoana de la care au fost prelevate impresiunile papilare pentru comparație;",
      "dacă impresiunile papilare înaintate conțin suficiente detalii dactiloscopice macroscopice calitative si cantitative necesare efectuării comparațiilor dactiloscopice;"
    ]
  },
  {
    titlu: "EXPERTIZA BALISTCĂ A ARMELOR ȘI MUNIȚIILOR",
    intrebari: [
      "clasificarea armei din punct de vedere constructiv;",
      "dacă arma prezentată face parte din categoria armelor de foc sau a altor categorii de arme sau este o componenta a unei arme de foc;",
      "stabilirea mărcii, tipului, calibrului, modelului, țării producătoare, pe baza caracteristicilor constructive;",
      "dacă este confecționată industrial sau artizanal ori dacă prezinta modificări tehnice de natură artizanală;",
      "stabilirea stării de funcționare a armei de foc;",
      "relevarea seriei modificate, distruse/ înlăturate;",
      "dacă muniția este confecționată industrial sau artizanal ori dacă prezinta modificări tehnice de natură artizanală;",
      "dacă elementele separate puse la dispoziție pentru examinare (capsa de aprindere, pulbere propulsivă, tub-cartuș, glonț, etc.) sunt componente de muniție destinată armelor de foc;"
    ]
  }
];


</script>

<template>
  <section id="detalii" class="detailed-container">
    <div class="content">
      
      <h3 class="main-title">Probleme care pot fi rezolvate și întrebări la care putem răspunde prin expertiza criminalistică</h3>
      
      <div class="text-block" v-for="(item, index) in expertize" :key="'exp-'+index">
        <h4 class="category-title">{{ item.titlu }}</h4>
        <ul class="clean-list">
          <li v-for="(intrebare, idx) in item.intrebari" :key="idx">
            {{ intrebare }}
          </li>
        </ul>
      </div>

      
      
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
.detailed-container {
  padding: 80px 20px;
  background-color: white; /* Fundal simplu, curat */
}

.content {
  max-width: 900px; /* Lățime optimă pentru citirea unui text lung, ca într-o carte */
  margin: 0 auto;
}

.main-title {
  font-size: 2rem;
  color: var(--primary-color);
  margin-bottom: 40px;
  text-align: left;
  border-bottom: 2px solid var(--primary-color);
  padding-bottom: 15px;
  line-height: 1.3;
}

.category-title {
  font-size: 1.2rem;
  color: var(--primary-color);
  margin-top: 40px;
  margin-bottom: 15px;
  text-transform: uppercase;
  letter-spacing: 0.5px;
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
}

/* Stilizarea listelor "normale" */
.clean-list {
  list-style-type: disc; /* Puncte clasice negre */
  padding-left: 20px;
  margin: 0;
}

.clean-list li {
  margin-bottom: 10px;
  font-size: 1.05rem;
  line-height: 1.6;
  color: var(--text-dark);
}

.law-list li {
  margin-bottom: 15px;
  text-align: justify;
}

.divider {
  height: 1px;
  background-color: #cbd5e1;
  margin: 60px 0;
}

@media (max-width: 768px) {
  .main-title {
    font-size: 1.6rem;
  }
  .intro-text, .clean-list li {
    text-align: left; /* Pe mobil renunțăm la justify */
  }
}
</style>