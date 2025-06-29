<template>
  <div class="education-item" :class="{ 'education-item-last': last }">
    <div class="education-icon">
      <font-awesome-icon :icon="['fas', 'graduation-cap']" />
    </div>
    <div class="education-content">
      <h3>{{ school }}</h3>
      <h4>{{ course }}</h4>
      <p>{{ desc }}</p>
    </div>
  </div>
</template>

<script>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'

export default {
  name: 'EducationItem',
  components: {
    FontAwesomeIcon
  },
  props: {
    school: {
      type: String,
      required: true
    },
    course: {
      type: String,
      required: true
    },
    desc: {
      type: String,
      required: true
    },
    last: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped>
.education-item {
  display: flex;
  align-items: flex-start;
  padding-bottom: 2rem;
  border-bottom: 1px solid #eee;
  margin-bottom: 2rem;
  transition: transform 0.3s ease;
}

.education-item:hover {
  transform: translateX(10px);
}

.education-item-last {
  border-bottom: none;
  padding-bottom: 0;
  margin-bottom: 0;
}

.education-icon {
  background: linear-gradient(135deg, #007bff, #0056b3);
  color: white;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-right: 1.5rem;
  flex-shrink: 0;
  font-size: 1.2rem;
}

.education-content h3 {
  color: #333;
  margin-bottom: 0.5rem;
  font-size: 1.2rem;
}

.education-content h4 {
  color: #007bff;
  margin-bottom: 0.5rem;
  font-size: 1rem;
  font-weight: 600;
}

.education-content p {
  color: #666;
  line-height: 1.6;
}

@media (max-width: 768px) {
  .education-item {
    flex-direction: column;
    text-align: center;
  }
  
  .education-icon {
    margin-right: 0;
    margin-bottom: 1rem;
    align-self: center;
  }
}
</style>
