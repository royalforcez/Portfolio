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
  background: transparent;
  padding: 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative;
  overflow: hidden;
}

.irts-gallery::before {
  content: none;
}

.gallery-container {
  position: relative;
  z-index: 1;
  max-width: 1200px;
  width: 100%;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 2.5rem;
  flex-wrap: wrap;
  padding: 1rem;
}

.gallery-item {
  width: 300px;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 0 auto;
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
  background: var(--white);
  border: 1px solid var(--border-light);
  box-shadow: 0 8px 25px rgba(59, 93, 143, 0.1);
  transition: all 0.3s ease;
}

.photo-frame::before {
  content: none;
}

.photo-frame:hover {
  transform: translateY(-8px);
  box-shadow: 0 15px 35px rgba(59, 93, 143, 0.15);
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
  color: var(--pastel-navy);
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
  background: linear-gradient(to right, var(--pastel-purple), var(--pastel-teal));
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