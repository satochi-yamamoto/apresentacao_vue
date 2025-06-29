<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <div class="footer-logo">
          <a href="#">{{ personalInfo.name }}</a>
        </div>
        <div class="footer-links">
          <ul>
            <li><a href="#about">Sobre</a></li>
            <li><a href="#experience">Experiência</a></li>
            <li><a href="#education">Formação</a></li>
            <li><a href="#skills">Habilidades</a></li>
            <li><a href="#projects">Projetos</a></li>
            <li><a href="#contact">Contato</a></li>
          </ul>
        </div>
      </div>
      <div class="footer-copyright">
        <p>&copy; {{ currentYear }} {{ personalInfo.name }}. Todos os direitos reservados.</p>
      </div>
    </div>
  </footer>
</template>

<script>
import { ref } from 'vue'
import { personalInfo } from '../data/portfolioData.js'

export default {
  name: 'Footer',
  setup() {
    const currentYear = ref(new Date().getFullYear())

    return {
      currentYear,
      personalInfo
    }
  }
}
</script>

<style scoped>
/* Estilos específicos do footer são herdados do CSS global */
</style>
