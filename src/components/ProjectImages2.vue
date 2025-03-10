<template>
  <section class="project-images">
    <div class="images-container">
      
      <div class="image-card">
        <div class="image-wrapper">
          <img src="/src/assets/image_profile.png" alt="Titre Image 1">
        </div>
        <div class="image-title">
          Titre Image 1
        </div>
      </div>

      
      <div class="image-card">
        <div class="image-wrapper">
          <img src="/src/assets/image_profile.png" alt="Titre Image 2">
        </div>
        <div class="image-title">
          Titre Image 2
        </div>
      </div>

      
      <div class="image-card">
        <div class="image-wrapper">
          <img src="/src/assets/image_profile.png" alt="Titre Image 3">
        </div>
        <div class="image-title">
          Titre Image 3
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ProjectImages2'
}
</script>

<style scoped>
.project-images {
  min-height: 100vh;
  background: linear-gradient(135deg, var(--primary-blue) 0%, #1a2a3d 100%);
  padding: 3rem 2rem;
  display: flex;
  align-items: center;
}

.images-container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  gap: 2rem;
  flex-wrap: wrap;
}

.image-card {
  width: 300px;
}

.image-wrapper {
  position: relative;
  border-radius: 8px;
  overflow: hidden;
  border: 1px solid rgba(255, 255, 255, 0.2);
  background: rgba(255, 255, 255, 0.1);
  transition: transform 0.3s ease;
}

.image-wrapper:hover {
  transform: translateY(-5px);
}

img {
  width: 100%;
  height: 220px;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.image-wrapper:hover img {
  transform: scale(1.05);
}

.image-title {
  color: var(--white);
  font-size: 1.2rem;
  text-align: center;
  margin-top: 1rem;
}

@media (max-width: 768px) {
  .image-card {
    width: 100%;
    max-width: 320px;
  }
}
</style> 