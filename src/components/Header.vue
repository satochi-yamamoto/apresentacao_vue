<template>
  <header class="header">
    <div class="container header-flex">
      <nav class="navbar" :class="{ active: isMenuOpen }">
        <ul>
          <li><a href="#about" @click="closeMenu">Sobre</a></li>
          <li><a href="#experience" @click="closeMenu">Experiência</a></li>
          <li><a href="#education" @click="closeMenu">Formação</a></li>
          <li><a href="#skills" @click="closeMenu">Habilidades</a></li>
          <li><a href="#projects" @click="closeMenu">Projetos</a></li>
          <li><a href="#volunteer" @click="closeMenu">Voluntário</a></li>
          <li><a href="#contact" @click="closeMenu">Contato</a></li>
        </ul>
      </nav>
      <div class="header-icons">
        <a 
          :href="personalInfo.github" 
          target="_blank" 
          rel="noopener noreferrer" 
          title="GitHub"
          aria-label="GitHub Profile"
        >
          <font-awesome-icon :icon="['fab', 'github']" />
        </a>
        <a 
          :href="personalInfo.linkedinUrl" 
          target="_blank" 
          rel="noopener noreferrer" 
          title="LinkedIn"
          aria-label="LinkedIn Profile"
        >
          <font-awesome-icon :icon="['fab', 'linkedin']" />
        </a>
        <a 
          :href="personalInfo.discordUrl" 
          target="_blank" 
          rel="noopener noreferrer" 
          title="Discord"
          aria-label="Discord Profile"
        >
          <font-awesome-icon :icon="['fab', 'discord']" />
        </a>
      </div>
      <div class="mobile-menu" @click="toggleMenu" aria-label="Toggle menu">
        <font-awesome-icon :icon="['fas', 'bars']" />
      </div>
    </div>
  </header>
</template>

<script>
import { ref } from 'vue'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { personalInfo } from '../data/portfolioData.js'

export default {
  name: 'Header',
  components: {
    FontAwesomeIcon
  },
  setup() {
    const isMenuOpen = ref(false)

    const toggleMenu = () => {
      isMenuOpen.value = !isMenuOpen.value
    }

    const closeMenu = () => {
      isMenuOpen.value = false
    }

    return {
      isMenuOpen,
      toggleMenu,
      closeMenu,
      personalInfo
    }
  }
}
</script>

<style scoped>
/* Estilos específicos do header são herdados do CSS global */
</style>
