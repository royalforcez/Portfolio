<template>
  <section class="project-images">
    <div class="images-container">
      
      <div class="image-card" @click="toggleZoom(0)">
        <div class="image-wrapper">
          <img src="/src/assets/concurrence_MD.png" alt="Concurrence">
        </div>
        <div class="image-title">
          Concurrence
        </div>
      </div>

      
      <div class="image-card" @click="toggleZoom(1)">
        <div class="image-wrapper">
          <img src="/src/assets/swot_MD.png" alt="SWOT">
        </div>
        <div class="image-title">
          SWOT
        </div>
      </div>

      
      <div class="image-card" @click="toggleZoom(2)">
        <div class="image-wrapper">
          <img src="/src/assets/persona_MD.png" alt="Personas">
        </div>
        <div class="image-title">
          Personas
        </div>
      </div>
    </div>
    
    
    <div v-if="zoomedImageIndex !== null" class="image-zoom-overlay" @click="closeZoom">
      <div class="zoomed-image-container">
        <img :src="images[zoomedImageIndex]" alt="Image agrandie" @click.stop>
      </div>
    </div>
  </section>
</template>

<script>

import Concurrence from '@/assets/concurrence_MD.png'
import Swot from '@/assets/swot_MD.png'
import Persona from '@/assets/persona_MD.png'

export default {
  name: 'ProjectImages2',
  data() {
    return {
      zoomedImageIndex: null,
      images: [
        Concurrence,
        Swot,
        Persona
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
.project-images {
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

.project-images::before {
  content: none;
}

.section-title, .images-container {
  position: relative;
  z-index: 1;
}

.images-container {
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

.image-card {
  width: 300px;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 0 auto;
  transition: transform 0.3s ease;
}

.image-card:hover {
  transform: translateY(-10px);
}

.image-wrapper {
  position: relative;
  width: 100%;
  height: 450px;
  border-radius: 15px;
  overflow: hidden;
  background: var(--white);
  border: 1px solid var(--border-light);
  box-shadow: 0 8px 25px rgba(59, 93, 143, 0.1);
  transition: all 0.3s ease;
  cursor: zoom-in;
}

.image-wrapper::before {
  content: none;
}

.image-wrapper:hover {
  transform: translateY(-8px);
  box-shadow: 0 15px 35px rgba(59, 93, 143, 0.15);
}

img {
  width: 100%;
  height: 100%;
  object-fit: contain;
  transition: transform 0.5s ease;
  filter: brightness(1.05);
}

.image-wrapper:hover img {
  transform: scale(1.08);
}

.image-title {
  color: var(--pastel-navy);
  font-size: 1.2rem;
  text-align: center;
  margin-top: 1rem;
  font-weight: 700;
  letter-spacing: 0.5px;
  text-shadow: 1px 1px 2px rgba(255, 255, 255, 0.8);
  position: relative;
  display: inline-block;
}

.image-title::after {
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

.image-card:hover .image-title::after {
  width: 70%;
}

@media (max-width: 768px) {
  .image-card {
    width: 100%;
    max-width: 320px;
  }
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
  max-width: 90%;
  max-height: 90%;
  overflow: hidden;
  animation: zoom-in 0.3s ease;
}

.zoomed-image-container img {
  max-width: 100%;
  max-height: 90vh;
  object-fit: contain;
  cursor: zoom-out;
  box-shadow: 0 5px 30px rgba(0, 0, 0, 0.3);
}

@keyframes zoom-in {
  from {
    opacity: 0;
    transform: scale(0.8);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}
</style> 