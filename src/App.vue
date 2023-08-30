
<script setup>
  import LeftCard from '@/components/cards/LeftCard.vue';
  import RightCard from '@/components/cards/RightCard.vue';
  import About from '@/components/About.vue';
  import Contact from '@/components/Contact.vue';
  import Resume from '@/components/Resume.vue';
  import Portfolio from '@/components/Portfolio.vue';

import { ref } from 'vue';

const isSidebarActive = ref(false);
const toggleSidebar = () => {
  isSidebarActive.value = !isSidebarActive.value;
};
const pages = [
  { name: 'about', label: 'About' },
  { name: 'resume', label: 'Resume' },
  { name: 'portfolio', label: 'Portfolio' },
  { name: 'contact', label: 'Contact' },
];

const currentPage = ref('about'); // valor inicial

const setPage = (page) => {
  currentPage.value = page;
};
const isModalActive = ref(false);
const modalImg = ref('');
const modalAlt = ref('');
const modalTitle = ref('');
const modalText = ref('');

const toggleModal = () => {
  isModalActive.value = !isModalActive.value;
};

// Para los testimonios, cuando hagas clic en un ítem:
const onTestimonialClick = (item) => {
  modalImg.value = item.avatar;
  modalAlt.value = item.avatarAlt;
  modalTitle.value = item.title;
  modalText.value = item.text;
  toggleModal();
};

// Puedes seguir el mismo patrón para el resto de las secciones.
</script>
<template>
  <main>
    <LeftCard />
    <div class="main-content">

      <nav class="navbar">
        <ul class="navbar-list">
          <li v-for="page in pages" :key="page.name" class="navbar-item">
            <button 
              class="navbar-link" 
              :class="{ active: currentPage === page.name }" 
              @click="setPage(page.name)"
            >
              {{ page.label }}
            </button>
          </li>
        </ul>
      </nav>


      <template v-if="currentPage === 'about'">
        <About />
      </template>
      
      <template v-if="currentPage === 'resume'">
        <Resume />
      </template>

      <template v-if="currentPage === 'portfolio'">
        <Portfolio />
      </template>
      
      <template v-if="currentPage === 'contact'">
        <Contact />
      </template>
    </div>

  </main>

</template>

<!-- Resto del código ... -->

<style scoped>
  .portfolio {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%; /* Usar el 100% del ancho para ocupar todo el espacio */
    height: 100vh; /* Altura completa de la ventana del navegador */
    background-color: #121212;
    gap: 2rem;
  }

  /* Estilos para pantallas de tablet y móvil */
  @media (max-width: 1024px) {
    .portfolio {
      flex-direction: column; /* Alinea los elementos en una columna */
    }
  }
</style>
