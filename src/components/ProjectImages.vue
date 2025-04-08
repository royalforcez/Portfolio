<template>
  <section class="project-images">
    <div class="images-container">
      
      <div class="image-card">
        <div class="image-wrapper">
          <img src="/src/assets/image_profile.png" alt="Image 1">
        </div>
        <div class="image-title"></div>
      </div>

      
      <div class="image-card">
        <div class="image-wrapper">
          <img src="/src/assets/image_profile.png" alt="Image 2">
        </div>
        <div class="image-title"></div>
      </div>

      
      <div class="image-card">
        <div class="image-wrapper">
          <img src="/src/assets/image_profile.png" alt="Image 3">
        </div>
        <div class="image-title"></div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ProjectImages'
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

.images-container {
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
  height: 220px;
  border-radius: 15px;
  overflow: hidden;
  background: var(--white);
  border: 1px solid var(--border-light);
  box-shadow: 0 8px 25px rgba(59, 93, 143, 0.1);
  transition: all 0.3s ease;
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
  height: 220px;
  object-fit: cover;
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
  margin-top: 1.2rem;
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
</style> 