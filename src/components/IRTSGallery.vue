<template>
  <section class="irts-gallery">
    <div class="gallery-container">
      
      <div class="gallery-item" @click="toggleZoom(0)">
        <div class="photo-frame">
          <img src="/src/assets/Exterieur_IRTS_VR.png" alt="Extérieur" class="photo-image">
        </div>
        <div class="photo-title">Extérieur</div>
      </div>

      
      <div class="gallery-item" @click="toggleZoom(1)">
        <div class="photo-frame">
          <img src="/src/assets/Interieur_IRTS_VR.png" alt="Intérieur" class="photo-image">
        </div>
        <div class="photo-title">Intérieur</div>
      </div>

      
      <div class="gallery-item" @click="toggleZoom(2)">
        <div class="photo-frame">
          <img src="/src/assets/Trello_IRTS.png" alt="Trello" class="photo-image">
        </div>
        <div class="photo-title">Trello</div>
      </div>
    </div>
    
    <div v-if="zoomedImageIndex !== null" class="image-zoom-overlay" @click="closeZoom">
      <div class="zoomed-image-container">
        <img :src="images[zoomedImageIndex]" alt="Image agrandie" @click.stop class="zoomed-image">
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'IRTSGallery',
  data() {
    return {
      zoomedImageIndex: null,
      images: [
        '/src/assets/Exterieur_IRTS_VR.png',
        '/src/assets/Interieur_IRTS_VR.png',
        '/src/assets/Trello_IRTS.png'
      ]
    }
  },
  methods: {
    toggleZoom(index) {
      this.zoomedImageIndex = index;
    },
    closeZoom() {
      this.zoomedImageIndex = null;
    }
  }
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
  cursor: zoom-in;
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

/* Styles pour le zoom des images */
.image-zoom-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.85);
  z-index: 1000;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}

.zoomed-image-container {
  max-width: 100%;
  max-height: 100%;
  overflow: hidden;
  animation: zoom-in 0.5s ease forwards;
}

.zoomed-image-container img {
  max-width: 100%;
  max-height: 100vh;
  object-fit: contain;
  cursor: zoom-out;
  box-shadow: 0 5px 30px rgba(0, 0, 0, 0.3);
  transform: scale(1.0);
}

@keyframes zoom-in {
  from {
    opacity: 0;
    transform: scale(0.4);
  }
  to {
    opacity: 1;
    transform: scale(1.0);
  }
}

@media (max-width: 768px) {
  .gallery-item {
    width: 100%;
    max-width: 320px;
  }
}
</style> 