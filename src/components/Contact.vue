<template>
  <section id="contact" class="section contact">
    <div class="container">
      <h2 class="section-title">Entre em Contato</h2>
      <div class="contact-content">
        <div class="contact-info">
          <div class="info-item">
            <font-awesome-icon :icon="['fas', 'envelope']" />
            <span>{{ personalInfo.email }}</span>
          </div>
          <div class="info-item">
            <font-awesome-icon :icon="['fab', 'linkedin']" />
            <span>{{ personalInfo.linkedin }}</span>
          </div>
          <div class="info-item">
            <font-awesome-icon :icon="['fab', 'github']" />
            <span>GitHub: satochi-yamamoto</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { personalInfo } from '../data/portfolioData.js'

export default {
  name: 'Contact',
  components: {
    FontAwesomeIcon
  },
  setup() {
    return {
      personalInfo
    }
  }
}
</script>

<style scoped>
/* Estilos específicos do contact são herdados do CSS global */
</style>
