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
  background: var(--page-bg);
  padding: 3rem 2rem;
  position: relative;
  overflow: hidden;
}

.marketing-project::before {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  right: -50%;
  bottom: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(ellipse at center, var(--page-bg-alt) 0%, var(--page-bg) 70%);
  animation: gentle-breathing 18s ease-in-out infinite;
  z-index: 0;
}

@keyframes gentle-breathing {
  0%, 100% {
    transform: translate(-25%, -25%) rotate(0deg);
    opacity: 0.8;
  }
  33% {
    transform: translate(-25%, -25%) rotate(0.3deg);
    opacity: 0.9;
  }
  66% {
    transform: translate(-25%, -25%) rotate(-0.3deg);
    opacity: 1;
  }
}

.section-title, .pdf-download, .sections-container {
  position: relative;
  z-index: 1;
}

.section-title {
  color: var(--pastel-purple);
  font-size: 2.5rem;
  text-align: center;
  margin-bottom: 2.5rem;
  font-weight: 700;
  letter-spacing: 1px;
  text-shadow: 2px 2px 3px rgba(255, 255, 255, 0.8);
  position: relative;
  display: inline-block;
  left: 50%;
  transform: translateX(-50%);
}

.section-title::after {
  content: '';
  display: block;
  width: 80px;
  height: 4px;
  background: linear-gradient(to right, var(--pastel-purple), var(--pastel-teal));
  margin: 0.5rem auto 0;
  border-radius: 2px;
}

.sections-container {
  max-width: 1000px;
  margin: 0 auto;
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 2.5rem;
  padding: 0 1rem;
}

.project-section {
  flex: 1;
  max-width: 500px;
  border-radius: 15px;
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
  border-radius: 15px;
  border: 2px solid transparent;
  background-clip: padding-box;
  position: relative;
  z-index: 1;
  background: rgba(255, 255, 255, 0.85);
  transition: all 0.3s ease;
  box-shadow: 0 6px 20px rgba(106, 90, 205, 0.2),
              inset 0 0 15px rgba(255, 255, 255, 0.6);
}

.section-header::before {
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
  opacity: 0.6;
  transition: opacity 0.3s ease;
}

.project-section.active .section-header {
  border-radius: 15px 15px 0 0;
}

.project-section.active .section-header::before {
  border-radius: 17px 17px 0 0;
  opacity: 1;
}

.section-header:hover::before {
  opacity: 0.8;
}

.section-header h3 {
  color: var(--pastel-navy);
  font-size: 1.4rem;
  margin: 0;
  font-weight: 700;
}

.arrow {
  width: 12px;
  height: 12px;
  border-right: 2px solid var(--pastel-navy);
  border-bottom: 2px solid var(--pastel-navy);
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
  padding: 1.8rem;
  border-radius: 0 0 15px 15px;
  border: 2px solid transparent;
  background-clip: padding-box;
  position: relative;
  z-index: 1;
  background: rgba(255, 255, 255, 0.85);
  box-shadow: 0 6px 20px rgba(106, 90, 205, 0.2),
              inset 0 0 15px rgba(255, 255, 255, 0.6);
}

.content-box::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: -1;
  margin: -2px;
  border-radius: 0 0 17px 17px;
  background: linear-gradient(45deg, var(--pastel-purple), var(--pastel-teal));
  opacity: 0.6;
}

.content-box p {
  color: var(--text-dark);
  font-size: 1rem;
  line-height: 1.7;
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
  padding: 1rem 2rem;
  background: rgba(255, 255, 255, 0.85);
  border: 2px solid transparent;
  background-clip: padding-box;
  position: relative;
  z-index: 1;
  border-radius: 12px;
  color: var(--pastel-navy);
  text-decoration: none;
  font-size: 1rem;
  font-weight: 700;
  transition: all 0.3s ease;
  box-shadow: 0 6px 20px rgba(106, 90, 205, 0.2),
              inset 0 0 15px rgba(255, 255, 255, 0.6);
}

.download-button::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: -1;
  margin: -2px;
  border-radius: 14px;
  background: linear-gradient(45deg, var(--pastel-purple), var(--pastel-teal));
  opacity: 0.6;
  transition: opacity 0.3s ease;
}

.download-button:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 25px rgba(106, 90, 205, 0.3),
              inset 0 0 15px rgba(255, 255, 255, 0.6);
}

.download-button:hover::before {
  opacity: 1;
}

.pdf-icon {
  width: 20px;
  height: 20px;
  stroke: var(--pastel-navy);
  transition: all 0.3s ease;
}

.download-button:hover .pdf-icon {
  stroke: var(--pastel-purple);
  transform: scale(1.1);
}

@media (max-width: 768px) {
  .sections-container {
    flex-direction: column;
    align-items: center;
    gap: 1.5rem;
  }

  .project-section {
    width: 100%;
  }
  
  .section-title {
    font-size: 2.2rem;
  }
}
</style> 