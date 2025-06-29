<template>
  <div class="timeline-item">
    <div class="timeline-date">{{ date }}</div>
    <div class="timeline-content" :class="{ 'timeline-content-odd': odd }">
      <h3>{{ company }}</h3>
      <h4>{{ role }}</h4>
      <p class="description">{{ desc }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ExperienceItem',
  props: {
    date: {
      type: String,
      required: true
    },
    company: {
      type: String,
      required: true
    },
    role: {
      type: String,
      required: true
    },
    desc: {
      type: String,
      required: true
    },
    odd: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped>
.timeline-item {
  position: relative;
  margin-bottom: 2rem;
}

.timeline-date {
  font-weight: bold;
  color: #007bff;
  margin-bottom: 0.5rem;
}

.timeline-content {
  background: #fff;
  padding: 1.5rem;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
  margin-right: 54%;
  transition: transform 0.3s ease;
}

.timeline-content:hover {
  transform: translateY(-5px);
}

.timeline-content-odd {
  margin-left: 54%;
  margin-right: 0;
}

.timeline-content h3 {
  color: #333;
  margin-bottom: 0.5rem;
  font-size: 1.2rem;
}

.timeline-content h4 {
  color: #666;
  margin-bottom: 1rem;
  font-size: 1rem;
  font-weight: 500;
}

.description {
  white-space: pre-line;
  color: #555;
  line-height: 1.6;
}

@media (max-width: 768px) {
  .timeline-content,
  .timeline-content-odd {
    margin-left: 0;
    margin-right: 0;
  }
}
</style>
