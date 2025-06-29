<template>
  <section class="hero">
    <div class="container hero-container">
      <div class="hero-content">
        <h1>{{ personalInfo.name }}</h1>
        <h2>{{ personalInfo.title }}</h2>
        <p>{{ personalInfo.description }}</p>
        <div class="hero-cta">
          <a href="#contact" class="btn btn-primary">Entre em Contato</a>
          <a href="#experience" class="btn btn-outline">Ver Experiência</a>
        </div>
      </div>
      <div class="hero-image">
        <img :src="personalInfo.avatar" :alt="personalInfo.name">
      </div>
    </div>
  </section>
</template>

<script>
import { personalInfo } from '../data/portfolioData.js'

export default {
  name: 'Hero',
  setup() {
    return {
      personalInfo
    }
  }
}
</script>

<style scoped>
/* Estilos específicos do hero são herdados do CSS global */
</style>
