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
  background: transparent;
  padding: 3rem 2rem;
  position: relative;
  overflow: hidden;
}

.projects::before {
  content: none;
}

.section-title, .projects-container {
  position: relative;
  z-index: 1;
}

.section-title {
  color: var(--pastel-navy);
  font-size: 2.5rem;
  text-align: center;
  margin-bottom: 3rem;
  font-weight: 600;
}

.projects-container {
  display: flex;
  justify-content: center;
  flex-wrap: nowrap;
  gap: 1.5rem;
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 1rem;
  overflow-x: auto;
}

.project-card {
  width: 260px;
  flex-shrink: 0;
  background: var(--white);
  border-radius: 15px;
  padding: 1.5rem;
  border: 1px solid var(--border-light);
  box-shadow: 0 8px 25px rgba(59, 93, 143, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.project-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 15px 35px rgba(59, 93, 143, 0.15);
}

.project-image {
  width: 100%;
  height: 180px;
  border-radius: 10px;
  overflow: hidden;
  margin-bottom: 1.2rem;
  border: 1px solid var(--border-light);
}

.project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.project-card:hover .project-image img {
  transform: scale(1.05);
}

.project-title {
  color: var(--pastel-navy);
  font-size: 1.4rem;
  margin-bottom: 0.8rem;
  text-align: center;
  font-weight: 600;
}

.project-description {
  color: var(--text-dark);
  font-size: 0.95rem;
  line-height: 1.6;
  text-align: center;
}

@media (max-width: 1200px) {
  .projects-container {
    flex-wrap: wrap;
  }
  
  .project-card {
    width: calc(50% - 1rem);
    max-width: 280px;
  }
}

@media (max-width: 768px) {
  .project-card {
    width: 100%;
    max-width: 320px;
  }
}
</style> 