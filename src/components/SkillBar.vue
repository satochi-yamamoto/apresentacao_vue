<template>
  <div class="skill-item">
    <div class="skill-header">
      <h3>{{ name }}</h3>
      <span class="skill-percentage">{{ level }}%</span>
    </div>
    <div class="skill-bar">
      <div 
        class="skill-level" 
        :style="{ width: level + '%' }"
        :data-level="level"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SkillBar',
  props: {
    name: {
      type: String,
      required: true
    },
    level: {
      type: Number,
      required: true,
      validator: (value) => value >= 0 && value <= 100
    }
  }
}
</script>

<style scoped>
.skill-item {
  margin-bottom: 2rem;
}

.skill-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 0.5rem;
}

.skill-header h3 {
  color: #333;
  font-size: 1rem;
  font-weight: 600;
  margin: 0;
}

.skill-percentage {
  color: #007bff;
  font-weight: bold;
  font-size: 0.9rem;
}

.skill-bar {
  background: #f0f0f0;
  height: 12px;
  border-radius: 6px;
  overflow: hidden;
  position: relative;
}

.skill-level {
  height: 100%;
  background: linear-gradient(90deg, #007bff, #0056b3);
  border-radius: 6px;
  transition: width 1.5s ease-out;
  position: relative;
}

.skill-level::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
  animation: shimmer 2s infinite;
}

@keyframes shimmer {
  0% { transform: translateX(-100%); }
  100% { transform: translateX(100%); }
}

.skill-item:hover .skill-level {
  box-shadow: 0 0 10px rgba(0, 123, 255, 0.5);
}

@media (max-width: 768px) {
  .skill-header {
    flex-direction: column;
    align-items: flex-start;
    gap: 0.25rem;
  }
  
  .skill-percentage {
    align-self: flex-end;
  }
}
</style>
