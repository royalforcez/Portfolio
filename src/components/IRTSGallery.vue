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
  background: linear-gradient(135deg, #0a192f 0%, var(--primary-blue) 100%);
  padding: 3rem 2rem;
  display: flex;
  align-items: center;
  justify-content: center;
}

.gallery-container {
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
}

.photo-frame {
  position: relative;
  width: 100%;
  height: 220px;
  border-radius: 8px;
  overflow: hidden;
  border: 1px solid rgba(255, 255, 255, 0.2);
  background: rgba(255, 255, 255, 0.1);
  transition: transform 0.3s ease;
}

.photo-frame:hover {
  transform: translateY(-5px);
}

.photo-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.photo-frame:hover .photo-image {
  transform: scale(1.05);
}

.photo-title {
  margin-top: 1rem;
  color: var(--white);
  font-size: 1.2rem;
  text-align: center;
}

@media (max-width: 768px) {
  .gallery-item {
    width: 100%;
    max-width: 320px;
  }
}
</style> 