<template>
  <div class="posts-list">
    <h2>Lista de Posts</h2>
    <ul>
      <li v-for="post in posts" :key="post.id">
        <strong>{{ post.title }}</strong>
        <p>{{ post.content }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'PostsList',
  props: {
    posts: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>
.posts-list {
  text-align: left; /* Alinhar lista à esquerda */
  margin-top: 20px;
}

/* Estilização da lista */
ul {
  list-style: none;
  padding: 0;
}

li {
  background: #e3e3e3;
  margin-bottom: 8px;
  padding: 12px;
  border-radius: 4px;
}

/* Título da lista */
h2 {
  text-align: center;
  margin-bottom: 10px;
}
</style>
