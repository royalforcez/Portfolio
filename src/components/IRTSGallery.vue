<template>
  <section class="irts-gallery">
    <div class="gallery-container">
      
      <div class="gallery-item">
        <div class="photo-frame">
          <img src="/src/assets/image_profile.png" alt="Vue d'ensemble" class="photo-image">
        </div>
        <div class="photo-title">Vue d'ensemble</div>
      </div>

      
      <div class="gallery-item">
        <div class="photo-frame">
          <img src="/src/assets/image_profile.png" alt="Interface utilisateur" class="photo-image">
        </div>
        <div class="photo-title">Interface utilisateur</div>
      </div>

      
      <div class="gallery-item">
        <div class="photo-frame">
          <img src="/src/assets/image_profile.png" alt="Environnement virtuel" class="photo-image">
        </div>
        <div class="photo-title">Environnement virtuel</div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'IRTSGallery'
}
</script>

<style scoped>
.irts-gallery {
  min-height: 100vh;
  background: var(--page-bg);
  padding: 3rem 2rem;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
}

.irts-gallery::before {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  right: -50%;
  bottom: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(ellipse at center, var(--page-bg-alt) 0%, var(--page-bg) 70%);
  animation: soft-ripple 20s ease-in-out infinite;
  z-index: 0;
}

@keyframes soft-ripple {
  0%, 100% {
    transform: translate(-25%, -25%) scale(1);
  }
  20% {
    transform: translate(-26%, -24%) scale(1.01);
  }
  40% {
    transform: translate(-24%, -26%) scale(0.99);
  }
  60% {
    transform: translate(-23%, -25%) scale(1.01);
  }
  80% {
    transform: translate(-25%, -23%) scale(0.99);
  }
}

.gallery-container {
  position: relative;
  z-index: 1;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.gallery-item {
  width: 300px;
  display: flex;
  flex-direction: column;
  align-items: center;
  transition: transform 0.3s ease;
}

.gallery-item:hover {
  transform: translateY(-10px);
}

.photo-frame {
  position: relative;
  width: 100%;
  height: 220px;
  border-radius: 15px;
  overflow: hidden;
  border: 3px solid transparent;
  background-clip: padding-box;
  position: relative;
  z-index: 1;
  background: rgba(255, 255, 255, 0.85);
  box-shadow: 0 8px 25px rgba(106, 90, 205, 0.2);
  transition: all 0.3s ease;
}

.photo-frame::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: -1;
  margin: -3px;
  border-radius: 18px;
  background: linear-gradient(45deg, var(--pastel-gold), var(--pastel-coral));
  opacity: 0.7;
  transition: opacity 0.3s ease;
}

.photo-frame:hover {
  box-shadow: 0 15px 35px rgba(106, 90, 205, 0.3),
              0 0 20px rgba(255, 163, 67, 0.4);
}

.photo-frame:hover::before {
  opacity: 1;
}

.photo-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.5s ease;
  filter: brightness(1.05);
}

.photo-frame:hover .photo-image {
  transform: scale(1.08);
}

.photo-title {
  margin-top: 1.2rem;
  color: var(--pastel-gold);
  font-size: 1.2rem;
  text-align: center;
  font-weight: 700;
  letter-spacing: 0.5px;
  text-shadow: 1px 1px 2px rgba(255, 255, 255, 0.8);
  position: relative;
  display: inline-block;
}

.photo-title::after {
  content: '';
  position: absolute;
  bottom: -6px;
  left: 50%;
  transform: translateX(-50%);
  width: 0;
  height: 2px;
  background: linear-gradient(to right, var(--pastel-gold), var(--pastel-coral));
  transition: width 0.3s ease;
}

.gallery-item:hover .photo-title::after {
  width: 70%;
}

@media (max-width: 768px) {
  .gallery-item {
    width: 100%;
    max-width: 320px;
  }
}
</style> 