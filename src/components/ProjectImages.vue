<template>
  <section class="project-images">
    <div class="images-container">
      
      <div class="image-card">
        <div class="image-wrapper">
          <img src="/src/assets/image_profile.png" alt="Image 1">
        </div>
        <div class="image-title">Titre Image 1</div>
      </div>

      
      <div class="image-card">
        <div class="image-wrapper">
          <img src="/src/assets/image_profile.png" alt="Image 2">
        </div>
        <div class="image-title">YOPPPPPPPP</div>
      </div>

      
      <div class="image-card">
        <div class="image-wrapper">
          <img src="/src/assets/image_profile.png" alt="Image 3">
        </div>
        <div class="image-title">Titre Image 3</div>
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
  background: var(--page-bg);
  padding: 3rem 2rem;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
}

.project-images::before {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  right: -50%;
  bottom: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(ellipse at center, var(--page-bg-alt) 0%, var(--page-bg) 70%);
  animation: gentle-float 15s ease-in-out infinite;
  z-index: 0;
}

@keyframes gentle-float {
  0%, 100% {
    transform: translate(-25%, -25%) rotate(0deg);
  }
  25% {
    transform: translate(-26%, -24%) rotate(0.3deg);
  }
  50% {
    transform: translate(-24%, -25%) rotate(-0.3deg);
  }
  75% {
    transform: translate(-25%, -26%) rotate(0deg);
  }
}

.images-container {
  position: relative;
  z-index: 1;
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  gap: 2.5rem;
  flex-wrap: wrap;
}

.image-card {
  width: 320px;
  display: flex;
  flex-direction: column;
  align-items: center;
  transition: transform 0.3s ease;
}

.image-card:hover {
  transform: translateY(-10px);
}

.image-wrapper {
  position: relative;
  width: 100%;
  border-radius: 15px;
  overflow: hidden;
  border: 3px solid transparent;
  background-clip: padding-box;
  position: relative;
  z-index: 1;
  box-shadow: 0 8px 25px rgba(106, 90, 205, 0.2);
  transition: all 0.3s ease;
}

.image-wrapper::before {
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

.image-wrapper:hover {
  box-shadow: 0 15px 35px rgba(106, 90, 205, 0.3),
              0 0 20px rgba(32, 178, 170, 0.4);
}

.image-wrapper:hover::before {
  opacity: 1;
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