<script setup>
defineProps({
  project: {
    type: Object,
    required: true
  }
})
</script>

<template>
  <div class="project-card">
    <div class="project-image" :style="{ backgroundImage: `url(${project.image})` }">
      <div class="overlay">
        <span class="tech-badge" v-for="tech in project.technologies" :key="tech">
          {{ tech }}
        </span>
      </div>
    </div>
    <div class="project-info">
      <h3>{{ project.title }}</h3>
      <p>{{ project.description }}</p>
    </div>
  </div>
</template>

<style scoped>
.project-card {
  background: white;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s;
}

.project-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 12px rgba(0, 0, 0, 0.15);
}

.project-image {
  height: 200px;
  background-size: cover;
  background-position: center;
  position: relative;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(102, 126, 234, 0.9);
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  justify-content: center;
  align-items: center;
  padding: 1rem;
  opacity: 0;
  transition: opacity 0.3s;
}

.project-card:hover .overlay {
  opacity: 1;
}

.tech-badge {
  background: white;
  color: #667eea;
  padding: 0.25rem 0.75rem;
  border-radius: 15px;
  font-size: 0.8rem;
  font-weight: bold;
}

.project-info {
  padding: 1.5rem;
}

.project-info h3 {
  color: #333;
  margin-bottom: 0.5rem;
}

.project-info p {
  color: #666;
  line-height: 1.5;
}
</style>