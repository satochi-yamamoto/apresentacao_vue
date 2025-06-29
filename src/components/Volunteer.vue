<template>
  <section id="volunteer" class="section volunteer">
    <div class="container">
      <h2 class="section-title">Trabalho Voluntário</h2>
      <div class="volunteer-content" v-for="(vol, index) in volunteer" :key="index">
        <h3>{{ vol.title }}</h3>
        <p>{{ vol.desc }}</p>
      </div>
    </div>
  </section>
</template>

<script>
import { volunteer } from '../data/portfolioData.js'

export default {
  name: 'Volunteer',
  setup() {
    return {
      volunteer
    }
  }
}
</script>

<style scoped>
/* Estilos específicos do volunteer são herdados do CSS global */
</style>
