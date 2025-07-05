<template>
  <div class="form-container">
    <h2>Criar Post</h2>
    <form @submit.prevent="createPost">
      <div class="form-group">
        <label for="title">Título:</label>
        <input
          type="text"
          id="title"
          v-model="title"
          required
        />
      </div>

      <div class="form-group">
        <label for="content">Conteúdo:</label>
        <textarea
          id="content"
          rows="5"
          v-model="content"
          required
        ></textarea>
      </div>

      <div class="form-group">
        <label for="nome">Nome:</label>
        <textarea
          id="nome"
          v-model="nome"
          required
        ></textarea>
      </div>
      <button type="submit">Salvar</button>
    </form>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'CreatePostForm',
  data() {
    return {
      title: '',
      content: '',
      nome: ''
    }
  },
  methods: {
    async createPost() {
      try {
        const payload = {
          title: this.title,
          content: this.content,
          nome: this.nome
        }

        // Variável de ambiente: process.env.VUE_APP_API_URL
        await axios.post(`${process.env.VUE_APP_API_URL}/posts`, payload)

        alert('Post criado com sucesso!')

        // Limpando campos
        this.title = ''
        this.content = ''
        this.nome = ''

        // Emitindo evento para o componente pai atualizar a lista
        this.$emit('postCreated')
      } catch (error) {
        console.error('Erro ao criar post:', error)
      }
    }
  }
}
</script>

<style scoped>
/* Área do formulário */
.form-container {
  margin-bottom: 20px;
  text-align: left; /* Alinhar rótulos à esquerda */
}

/* Espaço entre os campos do formulário */
.form-group {
  margin-bottom: 10px;
}

/* Labels com negrito */
label {
  font-weight: bold;
}

/* Inputs e textarea com estilos básicos */
input,
textarea {
  width: 100%;
  padding: 8px;
  margin-top: 4px;
  box-sizing: border-box;
  border-radius: 4px;
  border: 1px solid #ccc;
}

/* H2 estilizado para destaque */
h2 {
  text-align: center; /* Centraliza o título no container */
  margin-bottom: 10px;
}
</style>
