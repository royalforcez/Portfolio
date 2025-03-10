<template>
  <section class="vr-project">
    <h2 class="section-title">IRTS</h2>

    
    <div class="youtube-link">
      <a href="https://www.youtube.com/watch?v=tghSiWsBJT4" 
         target="_blank"
         class="youtube-button">
        <svg class="yt-icon" viewBox="0 0 24 24" fill="currentColor">
          <path d="M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 0 0 .502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 0 0 2.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/>
        </svg>
        Voir la démonstration
      </a>
    </div>

    
    <div class="images-container">
      <div class="image-box">
        <img src="/src/assets/XR-3-varjo-header.png" alt="Varjo XR-3" class="project-image">
      </div>
      <div class="image-box">
        <img src="/src/assets/meta-quest-2.png" alt="Meta Quest 2" class="project-image">
      </div>
    </div>

    
    <div class="text-container">
      <div class="text-box">
        <h3 class="text-title">Présentation</h3>
        <div class="text-content">
          <p>Description</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.vr-project {
  min-height: 100vh;
  background: linear-gradient(135deg, var(--primary-blue) 0%, #0a192f 100%);
  padding: 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.section-title {
  color: var(--white);
  font-size: 3rem;
  text-align: center;
  margin-bottom: 2rem;
}

.youtube-link {
  margin-bottom: 3rem;
}

.youtube-button {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1rem 2rem;
  background: rgba(52, 152, 219, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 10px;
  color: var(--white);
  text-decoration: none;
  font-size: 1.1rem;
  transition: background-color 0.3s ease;
}

.youtube-button:hover {
  background: rgba(52, 152, 219, 0.2);
}

.yt-icon {
  width: 24px;
  height: 24px;
  color: var(--white);
}

.images-container {
  width: 100%;
  max-width: 1200px;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  gap: 2rem;
  margin-bottom: 3rem;
}

.image-box {
  width: 300px;
  height: 200px;
  border-radius: 10px;
  overflow: hidden;
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.project-image {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.text-container {
  max-width: 800px;
  width: 100%;
}

.text-box {
  background: rgba(255, 255, 255, 0.1);
  border-radius: 10px;
  padding: 2rem;
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.text-title {
  font-size: 2rem;
  color: var(--white);
  text-align: center;
  margin-bottom: 1.5rem;
  text-transform: uppercase;
}

.text-content {
  color: var(--white);
  font-size: 1rem;
  line-height: 1.5;
}

@media (max-width: 768px) {
  .images-container {
    flex-direction: column;
    align-items: center;
  }
  
  .section-title {
    font-size: 2.5rem;
  }
  
  .text-title {
    font-size: 1.8rem;
  }
}
</style> 