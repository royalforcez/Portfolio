<template>
  <section class="projects">
    <div class="projects-container">
      <div v-for="(project, index) in projects" 
           :key="index"
           class="project-card">
        <div class="project-image">
          <img :src="project.image" :alt="project.title">
        </div>
        <div class="project-content">
          <h3 class="project-title">{{ project.title }}</h3>
          <p class="project-description">{{ project.description }}</p>
        </div>
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
      ],
      isTransitioning: false
    }
  },
  mounted() {
    const container = document.querySelector('.projects-container');
    const projectsSection = this.$el.closest('.snap-section');
    
    if (container) {
      // Gestionnaire pour le défilement horizontal
      container.addEventListener('wheel', (event) => {
        event.preventDefault();
        
        // Détecter la direction du défilement
        const isScrollingUp = event.deltaY < 0;
        
        // Si on défile vers le haut au début de la section des projets
        if (isScrollingUp && container.scrollLeft <= 10) {
          // Accélération du retour à la section précédente
          const previousSection = projectsSection.previousElementSibling;
          if (previousSection) {
            previousSection.scrollIntoView({ behavior: 'smooth' });
            return;
          }
        }
        
        // Augmenter la vitesse de défilement (facteur de 3)
        const scrollAmount = event.deltaY * 3;
        
        // Vérifier si on a atteint la fin du défilement
        if (container.scrollLeft + container.clientWidth + scrollAmount >= container.scrollWidth) {
          // Si c'est le dernier projet, afficher le dernier projet complètement d'abord
          if (!this.isTransitioning) {
            this.isTransitioning = true;
            
            // S'assurer que le dernier projet est entièrement visible
            const lastCardPosition = container.scrollWidth - container.clientWidth;
            container.scrollTo({
              left: lastCardPosition,
              behavior: 'smooth'
            });
            
            // Attendre 1,5 secondes avant de passer à la section suivante
            setTimeout(() => {
              const currentSection = this.$el.closest('.snap-section');
              const nextSection = currentSection.nextElementSibling;
              
              if (nextSection) {
                nextSection.scrollIntoView({ behavior: 'smooth' });
              }
              
              // Réinitialiser l'état après la transition
              setTimeout(() => {
                this.isTransitioning = false;
              }, 1000);
            }, 1500);
          }
        } else {
          // Sinon, continuer le défilement normal
          container.scrollLeft += scrollAmount;
        }
      }, { passive: false });
      
      // Ajouter un gestionnaire d'événements supplémentaire pour la section entière
      projectsSection.addEventListener('wheel', (event) => {
        // Si on est tout en haut de la section et qu'on défile vers le haut
        if (event.deltaY < 0 && container.scrollLeft <= 10) {
          const previousSection = projectsSection.previousElementSibling;
          if (previousSection) {
            previousSection.scrollIntoView({ behavior: 'smooth' });
          }
        }
      }, { passive: false });
    }
  },
  beforeUnmount() {
    const container = document.querySelector('.projects-container');
    if (container) {
      container.removeEventListener('wheel', () => {});
    }
  }
}
</script>

<style scoped>
.projects {
  min-height: 100vh;
  background: transparent;
  padding: 2rem;
  position: relative;
  overflow: visible;
}

.projects-container {
  display: flex;
  flex-direction: row;
  gap: 2rem;
  overflow-x: scroll;
  scroll-behavior: smooth;
  -webkit-overflow-scrolling: touch;
  padding: 2rem 0;
  width: 100%;
  scrollbar-width: none; /* Firefox */
  -ms-overflow-style: none; /* IE and Edge */
  position: relative;
  cursor: grab;
  user-select: none;
}

.projects-container::-webkit-scrollbar {
  display: none; /* Chrome, Safari, Opera */
}

.projects-container:active {
  cursor: grabbing;
}

.project-card {
  width: 80vw;
  max-width: 1200px;
  height: 80vh;
  flex: 0 0 auto;
  background: var(--white);
  border-radius: 20px;
  padding: 2rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  box-shadow: 0 10px 30px rgba(59, 93, 143, 0.15);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  margin-right: 2rem;
  pointer-events: none;
}

.project-card:last-child {
  margin-right: 0;
}

.project-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 15px 40px rgba(59, 93, 143, 0.2);
}

.project-image {
  width: 100%;
  height: 60%;
  border-radius: 15px;
  overflow: hidden;
  margin-bottom: 2rem;
  box-shadow: 0 8px 25px rgba(59, 93, 143, 0.1);
}

.project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.5s ease;
}

.project-card:hover .project-image img {
  transform: scale(1.05);
}

.project-content {
  text-align: center;
  width: 100%;
  max-width: 800px;
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.5s ease, transform 0.5s ease;
}

.project-card:hover .project-content {
  opacity: 1;
  transform: translateY(0);
}

.project-title {
  color: var(--pastel-navy);
  font-size: 2.5rem;
  margin-bottom: 1.5rem;
  font-weight: 600;
}

.project-description {
  color: var(--text-dark);
  font-size: 1.2rem;
  line-height: 1.6;
}

@media (max-width: 768px) {
  .project-card {
    width: 90vw;
    height: 70vh;
  }
  
  .project-image {
    height: 50%;
  }
  
  .project-title {
    font-size: 2rem;
  }
  
  .project-description {
    font-size: 1rem;
  }
}
</style> 