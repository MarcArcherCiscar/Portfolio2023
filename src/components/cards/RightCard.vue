<script setup>
</script>

<template>
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
</template>