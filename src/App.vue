<template>
  <div class="container">
     
    <h1>Alexandre Satochi Yamamoto</h1>
                <h2>Coordenador de Desenvolvimento de Software e TI,</h2>
      <p>+25 anos de atuação na área de TI dos quais 12 anos dedicado a liderança de equipes em projetos de TI e de Desenvolvimento de Softwares</p>
           
    <!-- Conteúdo agrupará o formulário e a listagem -->
    <div class="content">
      <!-- Formulário para criar novos posts -->
      <create-post-form @postCreated="fetchPosts" />
      
      <!-- Lista de posts existentes, recebidos via data -->
      <posts-list :posts="posts" />
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import CreatePostForm from './components/CreatePostForm.vue'
import PostsList from './components/PostsList.vue'

export default {
  name: 'App',
  components: {
    CreatePostForm,
    PostsList
  },
  data() {
    return {
      posts: []
    }
  },
  methods: {
    async fetchPosts() {
      try {
        const response = await axios.get(`${process.env.VUE_APP_API_URL}/posts`)
        this.posts = response.data.data
      } catch (error) {
        console.error('Erro ao buscar posts:', error)
      }
    }
  },
  created() {
    // Carrega os posts ao iniciar
    this.fetchPosts()
  }
}
</script>

<style>
/* 
  Estilizando a página de forma geral 
  para ter um fundo de tela e centralizar conteúdo 
*/

/* Zera margens e preenchimentos padrões */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* Fundo da página com uma imagem de exemplo e cor de apoio */
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  background: #f0f0f0 url('https://via.placeholder.com/1600x900/cccccc/ffffff?text=Background+Image') no-repeat center center fixed;
  background-size: cover;
}

/* Container principal, centralizado e com um fundo semi-transparente */
.container {
  max-width: 800px;
  margin: 0 auto;
  text-align: center;         /* Centraliza textos */
  background: rgba(255, 255, 255, 0.9);
  padding: 40px;
  margin-top: 40px;
  border-radius: 8px;
}

/* Conteúdo interno que agrupa o formulário e a lista */
.content {
  background-color: #fafafa;
  border-radius: 8px;
  padding: 20px;
}

/* Título com espaçamento */
h1 {
  margin-bottom: 20px;
}

/* Ajustes de Botão */
button {
  background-color: #42b983; /* Verde padrão do Vue */
  color: white;
  border: none;
  padding: 10px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-size: 1rem;
}

button:hover {
  background-color: #36a773;
}
</style>
