<template>
    <article class="resume active" data-page="portfolio">

        <header>
          <h2 class="h2 article-title">Portfolio</h2>
        </header>
    
        <section class="projects">
    
          <ul class="filter-list">
            <li class="filter-item" v-for="category in categories" :key="category">
              <button :class="{ active: selectedCategory === category }" 
                      @click="selectedCategory = category" 
                      :data-filter-btn="true">
                {{ category }}
              </button>
            </li>
          </ul>
    
          <ul class="project-list">
            <li class="project-item active" v-for="project in filteredProjects" :key="project.title" 
                :data-filter-item="true" 
                :data-category="project.category">
              <a :href="project.link">
                <figure class="project-img">
                  <img :src="project.image" :alt="project.title" loading="lazy">
                </figure>
                <h3 class="project-title">{{ project.title }}</h3>
                <p class="project-category">{{ project.category }}</p>
              </a>
            </li>
          </ul>
    
        </section>

    </article>
</template>

<script>
export default {
  data() {
    return {
      selectedCategory: 'All',
      categories: ['All', 'Blockchain', 'Applications', 'Web development'],
      projects: [
        {
          title: 'Blockcoin',
          category: 'Web development & Blockchain',
          image: '../assets/images/works/blockcoin.png',
          link: '#'
        },
        {
          title: 'Airline',
          category: 'Web development & Blockchain',
          image: '../assets/images/works/airline.png',
          link: '#'
        },
        {
          title: 'Sharememes',
          category: 'Web development',
          image: '../assets/images/works/sharememes.png',
          link: '#'
        },
        {
          title: 'Discord bots',
          category: 'Applications & Web development',
          image: '../assets/images/works/discord-bots.jpg',
          link: '#'
        },
        {
          title: 'FriendsStream',
          category: 'Web development',
          image: '../assets/images/works/videochat.png',
          link: '#'
        },
        {
          title: 'MiTallerAdmin',
          category: 'Web development',
          image: '../assets/images/works/mitalleradmin.png',
          link: '#'
        }
      ]
    };
  },
  computed: {
    filteredProjects() {
      if (this.selectedCategory === 'All') {
        return this.projects;
      } else {
        return this.projects.filter(project => project.category.includes(this.selectedCategory));
      }
    },
  },
};
</script>