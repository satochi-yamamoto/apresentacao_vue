<template>
  <section id="projects" class="section projects">
    <div class="container">
      <h2 class="section-title">Projetos Destacados</h2>
      <div class="projects-grid">
        <ProjectCard
          v-for="(project, index) in projects"
          :key="index"
          :img="project.img"
          :title="project.title"
          :desc="project.desc"
          :link="project.link"
        />
      </div>
    </div>
  </section>
</template>

<script>
import ProjectCard from './ProjectCard.vue'
import { projects } from '../data/portfolioData.js'

export default {
  name: 'Projects',
  components: {
    ProjectCard
  },
  setup() {
    return {
      projects
    }
  }
}
</script>

<style scoped>
/* Estilos específicos dos projects são herdados do CSS global */
</style>
