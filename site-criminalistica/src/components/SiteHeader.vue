<script setup>
import { ref } from 'vue'; // Importăm 'ref' pentru a crea o variabilă interactivă

// Această variabilă ține minte starea meniului (fals = închis, adevărat = deschis)
const meniuDeschis = ref(false);

// Funcție care deschide/închide meniul la apăsarea pe buton
const schimbaMeniu = () => {
  meniuDeschis.value = !meniuDeschis.value;
};

const mergiLa = (id) => {
  const sectiune = document.getElementById(id);
  if (sectiune) {
    const y = sectiune.getBoundingClientRect().top + window.scrollY - 80;
    window.scrollTo({ top: y, behavior: 'smooth' });
  }
  // Ascundem meniul automat după ce utilizatorul a apăsat pe un link
  meniuDeschis.value = false;
};
</script>

<template>
  <header class="header-container">
    <div class="logo">
      <h3>Expertize Criminalistice</h3>
    </div>

    <button class="hamburger-btn" @click="schimbaMeniu">
      ☰
    </button>

    <nav class="nav-menu" :class="{ 'deschis': meniuDeschis }">
      <a href="#" @click.prevent="mergiLa('acasa')">Acasă</a>
      <a href="#" @click.prevent="mergiLa('despre')">Despre</a>
      <a href="#" @click.prevent="mergiLa('servicii')">Servicii</a>
      <a href="#" @click.prevent="mergiLa('legislatie')">Legislație</a>
      <a href="#" @click.prevent="mergiLa('contact')">Contact</a>
    </nav>
  </header>
</template>

<style scoped>
.header-container {
  background-color: var(--primary-color);
  color: var(--text-light);
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  position: sticky;
  top: 0;
  z-index: 1000;
  box-shadow: 0 2px 10px rgba(0,0,0,0.3);
}

.logo h3 {
  color: white;
  margin: 0;
  font-size: 1.5rem;
  font-weight: 700;
  letter-spacing: 1px;
}

.nav-menu {
  display: flex;
  gap: 20px;
}

.nav-menu a {
  color: #cbd5e1;
  font-weight: 500;
  transition: color 0.3s ease;
  cursor: pointer;
}

.nav-menu a:hover {
  color: white;
  border-bottom: 2px solid var(--accent-color);
}

/* NOU: Stilizăm butonul hamburger (ascuns pe calculatoare) */
.hamburger-btn {
  display: none;
  background: none;
  border: none;
  color: white;
  font-size: 2rem;
  cursor: pointer;
}

/* NOU: Reguli doar pentru ecrane mici (Telefon) */
@media (max-width: 768px) {
  .hamburger-btn {
    display: block; /* Arătăm butonul de meniu */
  }

  .nav-menu {
    /* Ascundem meniul orizontal standard */
    display: none; 
    
    /* Îl pregătim ca o listă verticală ascunsă sus */
    flex-direction: column;
    position: absolute;
    top: 100%; /* Imediat sub bara albastră */
    left: 0;
    width: 100%;
    background-color: var(--primary-color);
    padding: 10px 0;
    text-align: center;
    box-shadow: 0 10px 10px rgba(0,0,0,0.2);
  }

  /* Magia: Când apăsăm pe buton, se activează clasa 'deschis' */
  .nav-menu.deschis {
    display: flex;
  }

  .nav-menu a {
    padding: 15px 0; /* Spațiu mai mare pentru deget */
    font-size: 1.2rem;
    border-bottom: 1px solid rgba(255,255,255,0.05);
  }
}
</style>