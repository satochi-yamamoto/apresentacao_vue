<template>
  <div class="project-item">
    <div class="project-image">
      <img :src="img" :alt="title" @error="onImageError">
    </div>
    <div class="project-overlay">
      <h3>{{ title }}</h3>
      <p>{{ desc }}</p>
      <a 
        :href="link" 
        class="btn btn-outline" 
        target="_blank" 
        rel="noopener noreferrer"
        @click="handleLinkClick"
      >
        Ver Detalhes
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProjectCard',
  props: {
    img: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    desc: {
      type: String,
      required: true
    },
    link: {
      type: String,
      required: true
    }
  },
  methods: {
    onImageError(event) {
      console.warn(`Failed to load image: ${this.img}`);
      event.target.src = 'data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" width="300" height="200"%3E%3Crect width="100%25" height="100%25" fill="%23f0f0f0"/%3E%3Ctext x="50%25" y="50%25" text-anchor="middle" dy=".3em" fill="%23999"%3EImage not found%3C/text%3E%3C/svg%3E';
    },
    handleLinkClick(event) {
      if (this.link === '#') {
        event.preventDefault();
        alert('Este projeto ainda não possui link disponível.');
      }
    }
  }
}
</script>

<style scoped>
.project-item {
  position: relative;
  border-radius: 12px;
  overflow: hidden;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  background: #fff;
  box-shadow: 0 4px 15px rgba(0,0,0,0.1);
}

.project-item:hover {
  transform: translateY(-10px);
  box-shadow: 0 15px 30px rgba(0,0,0,0.2);
}

.project-image {
  width: 100%;
  height: 200px;
  overflow: hidden;
}

.project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.project-item:hover .project-image img {
  transform: scale(1.1);
}

.project-overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background: linear-gradient(transparent, rgba(0,0,0,0.8));
  color: #fff;
  padding: 2rem 1.5rem 1.5rem;
  transform: translateY(100%);
  transition: transform 0.3s ease;
}

.project-item:hover .project-overlay {
  transform: translateY(0);
}

.project-overlay h3 {
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
  color: #fff;
}

.project-overlay p {
  font-size: 0.9rem;
  margin-bottom: 1rem;
  line-height: 1.5;
  color: #f0f0f0;
}

.btn {
  display: inline-block;
  padding: 0.5rem 1rem;
  border-radius: 6px;
  text-decoration: none;
  transition: all 0.3s ease;
  font-weight: 500;
  text-align: center;
  cursor: pointer;
  border: none;
  font-size: 0.9rem;
}

.btn-outline {
  background: transparent;
  color: #fff;
  border: 2px solid #fff;
}

.btn-outline:hover {
  background: #fff;
  color: #333;
  transform: translateY(-2px);
}

@media (max-width: 768px) {
  .project-overlay {
    position: static;
    transform: none;
    background: linear-gradient(135deg, #333, #555);
    padding: 1rem;
  }
  
  .project-item:hover .project-overlay {
    transform: none;
  }
}
</style>
