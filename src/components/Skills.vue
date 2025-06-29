<template>
  <section id="skills" class="section skills">
    <div class="container">
      <h2 class="section-title">Habilidades</h2>
      <div class="skills-grid">
        <SkillBar 
          v-for="(skill, index) in skills" 
          :key="index" 
          :name="skill.name" 
          :level="skill.level" 
        />
      </div>
    </div>
  </section>
</template>

<script>
import SkillBar from './SkillBar.vue'
import { skills } from '../data/portfolioData.js'

export default {
  name: 'Skills',
  components: {
    SkillBar
  },
  setup() {
    return {
      skills
    }
  }
}
</script>

<style scoped>
/* Estilos específicos das skills são herdados do CSS global */
</style>
