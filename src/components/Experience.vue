<template>
  <section id="experience" class="section experience">
    <div class="container">
      <h2 class="section-title">Experiência Profissional</h2>
      <div class="timeline">
        <ExperienceItem
          v-for="(exp, index) in experiences"
          :key="index"
          :date="exp.date"
          :company="exp.company"
          :role="exp.role"
          :desc="exp.desc"
          :odd="index % 2 === 0"
        />
      </div>
    </div>
  </section>
</template>

<script>
import ExperienceItem from './ExperienceItem.vue'
import { experiences } from '../data/portfolioData.js'

export default {
  name: 'Experience',
  components: {
    ExperienceItem
  },
  setup() {
    return {
      experiences
    }
  }
}
</script>

<style scoped>
/* Estilos específicos da experience são herdados do CSS global */
</style>
