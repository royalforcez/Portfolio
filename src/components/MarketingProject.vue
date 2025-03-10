<template>
  <section class="marketing-project">
    <h2 class="section-title">Marketing Digital</h2>

    
    <div class="pdf-download">
      <a href="/src/assets/marketing-project.pdf" 
         download
         class="download-button">
        <svg class="pdf-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor">
          <path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z" 
                stroke-width="2" 
                stroke-linecap="round" 
                stroke-linejoin="round"/>
          <path d="M14 2v6h6" 
                stroke-width="2" 
                stroke-linecap="round" 
                stroke-linejoin="round"/>
          <path d="M12 18v-6" 
                stroke-width="2" 
                stroke-linecap="round" 
                stroke-linejoin="round"/>
          <path d="M8 15l4 4 4-4" 
                stroke-width="2" 
                stroke-linecap="round" 
                stroke-linejoin="round"/>
        </svg>
        Télécharger le PDF du projet
      </a>
    </div>

    <div class="sections-container">
      <div class="project-section" 
           :class="{ 'active': isContextOpen }"
           @click="toggleContext">
        <div class="section-header">
          <h3>Contexte</h3>
          <div class="arrow" :class="{ 'rotated': isContextOpen }"></div>
        </div>
        <div class="section-content" :class="{ 'expanded': isContextOpen }">
          <div class="content-box">
            <p>
              Texte
            </p>
          </div>
        </div>
      </div>

      <div class="project-section"
           :class="{ 'active': isPresentationOpen }"
           @click="togglePresentation">
        <div class="section-header">
          <h3>Présentation</h3>
          <div class="arrow" :class="{ 'rotated': isPresentationOpen }"></div>
        </div>
        <div class="section-content" :class="{ 'expanded': isPresentationOpen }">
          <div class="content-box">
            <p>
              Texte
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'MarketingProject',
  data() {
    return {
      isContextOpen: false,
      isPresentationOpen: false
    }
  },
  methods: {
    toggleContext() {
      this.isContextOpen = !this.isContextOpen
    },
    togglePresentation() {
      this.isPresentationOpen = !this.isPresentationOpen
    }
  }
}
</script>

<style scoped>
.marketing-project {
  min-height: 100vh;
  background: linear-gradient(135deg, var(--primary-blue) 0%, #1a2a3d 100%);
  padding: 2rem;
}

.section-title {
  color: var(--white);
  font-size: 2.5rem;
  text-align: center;
  margin-bottom: 2rem;
}

.sections-container {
  max-width: 1000px;
  margin: 0 auto;
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 2rem;
  padding: 0 1rem;
}

.project-section {
  flex: 1;
  max-width: 500px;
  border-radius: 10px;
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  flex-direction: column;
}

.section-header {
  padding: 1.5rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-radius: 10px;
  border: 1px solid rgba(255, 255, 255, 0.2);
  background: rgba(255, 255, 255, 0.1);
}

.project-section.active .section-header {
  border-radius: 10px 10px 0 0;
}

.section-header h3 {
  color: var(--white);
  font-size: 1.5rem;
  margin: 0;
}

.arrow {
  width: 15px;
  height: 15px;
  border-right: 2px solid var(--secondary-blue);
  border-bottom: 2px solid var(--secondary-blue);
  transform: rotate(45deg);
  transition: transform 0.3s ease;
}

.arrow.rotated {
  transform: rotate(-135deg);
}

.section-content {
  max-height: 0;
  overflow: hidden;
  transition: all 0.3s ease-in-out;
  opacity: 0;
}

.section-content.expanded {
  max-height: 500px;
  opacity: 1;
}

.content-box {
  padding: 1.5rem;
  border-radius: 0 0 10px 10px;
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-top: none;
  background: rgba(255, 255, 255, 0.1);
}

.content-box p {
  color: var(--white);
  font-size: 1rem;
  line-height: 1.5;
  margin: 0;
}

.pdf-download {
  display: flex;
  justify-content: center;
  margin-bottom: 3rem;
}

.download-button {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 0.8rem 1.5rem;
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 10px;
  color: var(--white);
  text-decoration: none;
  font-size: 1rem;
  transition: all 0.3s ease;
}

.download-button:hover {
  background: rgba(255, 255, 255, 0.2);
}

.pdf-icon {
  width: 20px;
  height: 20px;
  stroke: var(--white);
}

@media (max-width: 768px) {
  .sections-container {
    flex-direction: column;
    align-items: center;
  }

  .project-section {
    width: 100%;
  }
  
  .section-title {
    font-size: 2rem;
  }
}
</style> 