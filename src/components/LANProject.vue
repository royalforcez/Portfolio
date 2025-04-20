<template>
  <div class="project-container">
    <h1 class="page-title">LAN</h1>
    <div class="content-wrapper">
      
      <div class="text-content">
        <div class="description-container">
          <p class="description-text">
            Et nous arrivons enfin à ce dernier projet, qui est à mon sens l'un des plus ambiatieux de ces deux dernières années.<br>
            Celui-ci est né d'une simple discussion en Octobre avec Jacques, notre responsable du MyDIL.<br>
            Suite à cette discussion, je me suis proposé pour être chef de projet de l'EPSI LAN qui aura lieu en Juillet 2025.<br>
            J'ai donc rassemblé des élèves de ma classe pour construire le projet ensemble.<br>
            Actuellement l'ensemble des serveurs sont prêts à être exploités, il nous reste à l'organisation de l'événement.<br>
            L'objectif de ce projet était de réunir les étudiants dans un projet commun au profit des autres étudiants et de créer un événement poiur rassembler les gens durant un week-end.

          </p>
        </div>
      </div>
      
      <div class="image-container">
        <img src="/src/assets/image_profile.png" alt="LAN Project Image" class="project-image" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LANProject'
}
</script>

<style scoped>
.project-container {
  min-height: 100vh;
  background: transparent;
  padding: 3rem 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  overflow: hidden;
}

.page-title {
  color: var(--pastel-purple);
  font-size: 3rem;
  margin-bottom: 3.5rem;
  text-align: center;
  font-weight: 700;
  letter-spacing: 1px;
  text-shadow: 2px 2px 3px rgba(255, 255, 255, 0.8);
  position: relative;
  display: inline-block;
}

.page-title::after {
  content: '';
  display: block;
  width: 80px;
  height: 4px;
  background: linear-gradient(to right, var(--pastel-purple), var(--pastel-teal));
  margin: 0.5rem auto 0;
  border-radius: 2px;
}

.content-wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1400px;
  width: 100%;
  gap: 3rem;
}

.text-content {
  flex: 1;
  padding-right: 2rem;
}

.description-container {
  background: rgba(255, 255, 255, 0.85);
  padding: 2rem;
  border-radius: 15px;
  box-shadow: 0 6px 20px rgba(106, 90, 205, 0.1);
  border: 2px solid transparent;
  background-clip: padding-box;
  position: relative;
}

.description-container::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: -1;
  margin: -2px;
  border-radius: 17px;
  background: linear-gradient(45deg, var(--pastel-purple), var(--pastel-teal));
  opacity: 0.3;
}

.description-text {
  color: var(--text-dark);
  font-size: 1.1rem;
  line-height: 1.8;
  text-align: justify;
}

.image-container {
  flex: 1;
  max-width: 600px;
}

.project-image {
  width: 100%;
  height: auto;
  border-radius: 15px;
  box-shadow: 0 8px 25px rgba(59, 93, 143, 0.1);
  transition: transform 0.3s ease;
}

.project-image:hover {
  transform: scale(1.02);
}

@media (max-width: 960px) {
  .content-wrapper {
    flex-direction: column;
    gap: 2rem;
  }

  .text-content {
    padding-right: 0;
    width: 100%;
  }

  .image-container {
    width: 100%;
    max-width: 100%;
  }

  .page-title {
    font-size: 2.5rem;
    margin-bottom: 2rem;
  }

  .description-container {
    padding: 1.5rem;
  }

  .description-text {
    font-size: 1rem;
  }
}
</style> 