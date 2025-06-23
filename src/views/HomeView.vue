<template>
  <div class="home">
    <h1>Bem-vindo ao Meu Site Vue.js</h1>
    <p>Este é um projeto de estudo para aprender Vue.js</p>
    
    <div class="features">
      <div v-for="feature in features" :key="feature.id" class="feature-card">
        <h3>{{ feature.title }}</h3>
        <p>{{ feature.description }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      features: [
        {
          id: 1,
          title: 'Componentes',
          description: 'Aprenda a criar componentes reutilizáveis'
        },
        {
          id: 2,
          title: 'Rotas',
          description: 'Navegação entre páginas com Vue Router'
        },
        {
          id: 3,
          title: 'Estado',
          description: 'Gerenciamento de estado com Pinia'
        }
      ]
    }
  }
}
</script>

<style scoped>
.home {
  max-width: 800px;
  margin: 0 auto;
}

.features {
  display: flex;
  justify-content: space-between;
  margin-top: 40px;
  flex-wrap: wrap;
}

.feature-card {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 20px;
  margin: 10px;
  width: 200px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}
</style>
