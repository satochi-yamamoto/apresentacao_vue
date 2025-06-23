<template>
  <div id="app">
    <h1>Bem-vindo ao meu site de teste em Vue!</h1>
    <MeuComponente />
  </div>
</template>

<script>
import MeuComponente from './components/MeuComponente.vue'

export default {
  name: 'App',
  components: {
    MeuComponente
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
  margin-top: 60px;
}
</style>
