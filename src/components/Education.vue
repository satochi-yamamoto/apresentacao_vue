<template>
  <section id="education" class="section education">
    <div class="container">
      <h2 class="section-title">Formação Acadêmica</h2>
      <div class="education-grid">
        <EducationItem
          v-for="(edu, index) in education"
          :key="index"
          :school="edu.school"
          :course="edu.course"
          :desc="edu.desc"
          :last="index === education.length - 1"
        />
      </div>
    </div>
  </section>
</template>

<script>
import EducationItem from './EducationItem.vue'
import { education } from '../data/portfolioData.js'

export default {
  name: 'Education',
  components: {
    EducationItem
  },
  setup() {
    return {
      education
    }
  }
}
</script>

<style scoped>
/* Estilos específicos da education são herdados do CSS global */
</style>
