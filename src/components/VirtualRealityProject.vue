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
  background: var(--page-bg);
  padding: 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  overflow: hidden;
}

.vr-project::before {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  right: -50%;
  bottom: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(ellipse at center, var(--page-bg-alt) 0%, var(--page-bg) 70%);
  animation: subtle-movement 18s ease-in-out infinite;
  z-index: 0;
}

@keyframes subtle-movement {
  0%, 100% {
    transform: translate(-25%, -25%) rotate(0deg);
  }
  25% {
    transform: translate(-26%, -25%) rotate(0.2deg);
  }
  50% {
    transform: translate(-25%, -24%) rotate(0deg);
  }
  75% {
    transform: translate(-24%, -25%) rotate(-0.2deg);
  }
}

.section-title, .youtube-link, .images-container, .text-container {
  position: relative;
  z-index: 1;
}

.section-title {
  color: var(--pastel-purple);
  font-size: 3rem;
  text-align: center;
  margin-bottom: 2rem;
  font-weight: 700;
  letter-spacing: 1px;
  text-shadow: 2px 2px 3px rgba(255, 255, 255, 0.8);
  position: relative;
  display: inline-block;
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

.youtube-link {
  margin-bottom: 3rem;
}

.youtube-button {
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
  font-size: 1.1rem;
  font-weight: 700;
  transition: all 0.3s ease;
  box-shadow: 0 6px 20px rgba(106, 90, 205, 0.2),
              inset 0 0 15px rgba(255, 255, 255, 0.6);
}

.youtube-button::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: -1;
  margin: -2px;
  border-radius: 14px;
  background: linear-gradient(45deg, var(--pastel-purple), var(--pastel-coral));
  opacity: 0.6;
  transition: opacity 0.3s ease;
}

.youtube-button:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 30px rgba(106, 90, 205, 0.3),
              inset 0 0 15px rgba(255, 255, 255, 0.6);
}

.youtube-button:hover::before {
  opacity: 1;
}

.yt-icon {
  width: 24px;
  height: 24px;
  color: var(--pastel-coral);
  transition: all 0.3s ease;
}

.youtube-button:hover .yt-icon {
  transform: scale(1.1);
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
  border-radius: 15px;
  overflow: hidden;
  border: 3px solid transparent;
  background-clip: padding-box;
  position: relative;
  z-index: 1;
  box-shadow: 0 8px 25px rgba(106, 90, 205, 0.2);
  transition: all 0.3s ease;
}

.image-box::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: -1;
  margin: -3px;
  border-radius: 18px;
  background: linear-gradient(45deg, var(--pastel-purple), var(--pastel-teal));
  opacity: 0.7;
  transition: opacity 0.3s ease;
}

.image-box:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 35px rgba(106, 90, 205, 0.3),
              0 0 20px rgba(32, 178, 170, 0.4);
}

.image-box:hover::before {
  opacity: 1;
}

.project-image {
  width: 100%;
  height: 100%;
  object-fit: contain;
  transition: transform 0.3s ease;
}

.image-box:hover .project-image {
  transform: scale(1.05);
}

.text-container {
  max-width: 800px;
  width: 100%;
}

.text-box {
  padding: 2rem;
  background: rgba(255, 255, 255, 0.85);
  border-radius: 15px;
  border: 2px solid transparent;
  background-clip: padding-box;
  position: relative;
  z-index: 1;
  box-shadow: 0 8px 25px rgba(106, 90, 205, 0.2),
              inset 0 0 15px rgba(255, 255, 255, 0.6);
}

.text-box::before {
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
}

.text-title {
  font-size: 2rem;
  color: var(--pastel-navy);
  text-align: center;
  margin-bottom: 1.5rem;
  text-transform: uppercase;
  font-weight: 700;
}

.text-content {
  color: var(--text-dark);
  font-size: 1rem;
  line-height: 1.5;
  position: relative;
  z-index: 1;
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