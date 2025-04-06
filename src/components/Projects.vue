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
          title: 'Marketing Digital',
          image: '/src/assets/derive_logo.png'
        },
        {
          title: 'IRTS',
          image: '/src/assets/IRTS_Project.png'
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
      isTransitioning: false,
      upScrollCount: 0,
      sectionUpScrollCount: 0,
      hasReachedEnd: false
    }
  },
  mounted() {
    const container = document.querySelector('.projects-container');
    const projectsSection = this.$el.closest('.snap-section');
    
    // Configurer l'effet de flou d'arrière-plan pour chaque image
    this.setupBlurEffects();
    
    if (container) {
      // Gestionnaire pour le défilement horizontal
      container.addEventListener('wheel', (event) => {
        event.preventDefault();
        
        // Détecter la direction du défilement
        const isScrollingUp = event.deltaY < 0;
        
        // Si on défile vers le haut au début de la section des projets
        // Ajouter une condition plus stricte pour éviter les déclenchements accidentels
        if (isScrollingUp && container.scrollLeft <= 10 && Math.abs(event.deltaY) > 50) {
          // Compteur pour éviter les activations accidentelles
          if (!this.upScrollCount) {
            this.upScrollCount = 1;
            // Réinitialiser après un court délai
            setTimeout(() => {
              this.upScrollCount = 0;
            }, 800);
            return;
          }
          
          this.upScrollCount++;
          
          // Ne remonter qu'après plusieurs défilements successifs vers le haut
          if (this.upScrollCount >= 3) {
            // Accélération du retour à la section précédente
            const previousSection = projectsSection.previousElementSibling;
            if (previousSection) {
              previousSection.scrollIntoView({ behavior: 'smooth' });
              this.upScrollCount = 0;
              return;
            }
          }
        } else if (!isScrollingUp) {
          // Réinitialiser le compteur quand on défile vers le bas
          this.upScrollCount = 0;
        }
        
        // Augmenter la vitesse de défilement (facteur de 3)
        const scrollAmount = event.deltaY * 3;
        
        // Vérifier si on a atteint la fin du défilement
        if (container.scrollLeft + container.clientWidth + scrollAmount >= container.scrollWidth) {
          // Si c'est le dernier projet, afficher le dernier projet complètement d'abord
          if (!this.isTransitioning) {
            this.isTransitioning = true;
            
            // Vérifier si l'utilisateur a déjà essayé de défiler au-delà
            if (this.hasReachedEnd) {
              // Si oui, naviguer immédiatement vers la section suivante
              const currentSection = this.$el.closest('.snap-section');
              const nextSection = currentSection.nextElementSibling;
              
              if (nextSection) {
                nextSection.scrollIntoView({ behavior: 'smooth' });
                
                // Réinitialiser les états
                setTimeout(() => {
                  this.isTransitioning = false;
                  this.hasReachedEnd = false;
                }, 1000);
              }
              return;
            }
            
            // Premier défilement à la fin, marquer l'état et montrer le dernier projet
            this.hasReachedEnd = true;
            
            // S'assurer que le dernier projet est entièrement visible
            const lastCardPosition = container.scrollWidth - container.clientWidth;
            container.scrollTo({
              left: lastCardPosition,
              behavior: 'smooth'
            });
            
            // Attendre un court délai avant de réinitialiser
            setTimeout(() => {
              this.isTransitioning = false;
            }, 500);
          }
        } else {
          // Réinitialiser l'indicateur de fin lorsqu'on n'est plus à la fin
          if (container.scrollLeft + container.clientWidth < container.scrollWidth - 50) {
            this.hasReachedEnd = false;
          }
          
          // Continuer le défilement normal
          container.scrollLeft += scrollAmount;
        }
      }, { passive: false });
      
      // Modifier le gestionnaire d'événements supplémentaire
      projectsSection.addEventListener('wheel', (event) => {
        // Ne déclencher que si le défilement est significatif et répété
        if (event.deltaY < -50 && container.scrollLeft <= 10) {
          if (!this.sectionUpScrollCount) {
            this.sectionUpScrollCount = 1;
            setTimeout(() => {
              this.sectionUpScrollCount = 0;
            }, 800);
            return;
          }
          
          this.sectionUpScrollCount++;
          
          if (this.sectionUpScrollCount >= 3) {
            const previousSection = projectsSection.previousElementSibling;
            if (previousSection) {
              previousSection.scrollIntoView({ behavior: 'smooth' });
              this.sectionUpScrollCount = 0;
            }
          }
        } else if (event.deltaY > 0) {
          this.sectionUpScrollCount = 0;
        }
      }, { passive: false });
    }
  },
  methods: {
    setupBlurEffects() {
      // Attendre que les images soient chargées
      setTimeout(() => {
        const imageContainers = document.querySelectorAll('.project-image');
        imageContainers.forEach((container, index) => {
          const img = container.querySelector('img');
          if (img) {
            // Si l'image est déjà chargée
            if (img.complete) {
              this.applyBlurEffect(container, img, index);
            } else {
              // Sinon attendre que l'image se charge
              img.onload = () => {
                this.applyBlurEffect(container, img, index);
              };
            }
          }
        });
      }, 300);
    },
    applyBlurEffect(container, img, index) {
      // Utiliser l'image comme arrière-plan flou
      const imgUrl = this.projects[index].image;
      container.style.setProperty('--image-url', `url(${imgUrl})`);
      img.style.opacity = '1';
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
  width: 50vw;
  max-width: 800px;
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
  height: 70%;
  border-radius: 15px;
  overflow: hidden;
  margin-bottom: 2rem;
  box-shadow: 0 8px 25px rgba(59, 93, 143, 0.1);
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 1rem;
  position: relative;
}

.project-image::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: var(--image-url);
  background-position: center;
  background-size: cover;
  filter: blur(20px) brightness(0.9);
  opacity: 0.7;
  transform: scale(1.2);
}

.project-image img {
  width: auto;
  height: auto;
  max-width: 100%;
  max-height: 100%;
  object-fit: contain;
  transition: transform 0.5s ease;
  position: relative;
  z-index: 1;
  opacity: 0;
}

.project-card:hover .project-image img {
  transform: scale(1.08);
}

.project-content {
  text-align: center;
  width: 100%;
  max-width: 800px;
  opacity: 1;
  transform: none;
  transition: opacity 0.5s ease, transform 0.5s ease;
  position: relative;
  z-index: 2;
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
    width: 80vw;
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