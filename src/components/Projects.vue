<template>
  <section class="projects">
    <h2 class="section-title">Mes Projets</h2>

    <div class="projects-container">
      <div v-for="(project, index) in projects" 
           :key="index"
           class="project-card">
        <div class="project-image">
          <img :src="project.image" :alt="project.title">
        </div>
        <h3 class="project-title">{{ project.title }}</h3>
        <p class="project-description">{{ project.description }}</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Projects',
  data() {
    return {
      projects: [
        {
          title: 'Projet 1',
          description: 'Description',
          image: '/src/assets/project1.jpg'
        },
        {
          title: 'Projet 2',
          description: 'Description',
          image: '/src/assets/project2.jpg'
        },
        {
          title: 'Projet 3',
          description: 'Description',
          image: '/src/assets/project3.jpg'
        },
        {
          title: 'Projet 4',
          description: 'Description',
          image: '/src/assets/project4.jpg'
        }
      ]
    }
  }
}
</script>

<style scoped>
.projects {
  min-height: 100vh;
  background: linear-gradient(135deg, var(--primary-blue) 0%, #1a2a3d 100%);
  padding: 2rem;
}

.section-title {
  color: var(--white);
  font-size: 2.5rem;
  text-align: center;
  margin-bottom: 3rem;
}

.projects-container {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.project-card {
  width: 280px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 10px;
  padding: 1rem;
  border: 1px solid rgba(255, 255, 255, 0.2);
  transition: transform 0.3s ease;
}

.project-card:hover {
  transform: translateY(-5px);
}

.project-image {
  width: 100%;
  height: 180px;
  border-radius: 8px;
  overflow: hidden;
  margin-bottom: 1rem;
}

.project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.project-title {
  color: var(--white);
  font-size: 1.4rem;
  margin-bottom: 0.5rem;
  text-align: center;
}

.project-description {
  color: var(--white);
  font-size: 0.9rem;
  line-height: 1.5;
  text-align: center;
}

@media (max-width: 768px) {
  .project-card {
    width: 100%;
    max-width: 320px;
  }
}
</style> 