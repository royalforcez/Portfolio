<template>
  <div class="project-container">
    <h1 class="page-title">Workshop Minecraft</h1>
    <div class="content-wrapper">
      
      <div class="image-container left">
        <img src="/src/assets/image_profile.png" alt="Workshop Minecraft Image 1" class="project-image" />
      </div>

      <div class="text-content">
        <div class="description-container">
          <p class="description-text">
            
          </p>
        </div>
      </div>
      
      <div class="image-container right">
        <img src="/src/assets/image_profile.png" alt="Workshop Minecraft Image 2" class="project-image" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'WorkshopMinecraft'
}
</script>

<style scoped>
.project-container {
  min-height: 100vh;
  background: transparent;
  padding: 3rem 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  overflow: hidden;
}

.page-title {
  color: var(--pastel-purple);
  font-size: 3rem;
  margin-bottom: 3.5rem;
  text-align: center;
  font-weight: 700;
  letter-spacing: 1px;
  text-shadow: 2px 2px 3px rgba(255, 255, 255, 0.8);
  position: relative;
  display: inline-block;
}

.page-title::after {
  content: '';
  display: block;
  width: 80px;
  height: 4px;
  background: linear-gradient(to right, var(--pastel-purple), var(--pastel-teal));
  margin: 0.5rem auto 0;
  border-radius: 2px;
}

.content-wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1400px;
  width: 100%;
  gap: 2rem;
}

.image-container {
  flex: 1;
  max-width: 400px;
}

.project-image {
  width: 100%;
  height: auto;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.text-content {
  flex: 2;
  padding: 0 3rem;
  max-width: 800px;
  margin: 0 auto;
}

.description-container {
  background: rgba(255, 255, 255, 0.85);
  padding: 2rem;
  border-radius: 15px;
  box-shadow: 0 6px 20px rgba(106, 90, 205, 0.1);
  margin: 1rem 0;
  border: 2px solid transparent;
  background-clip: padding-box;
  position: relative;
}

.description-container::before {
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
  opacity: 0.3;
}

.description-text {
  color: var(--text-dark);
  font-size: 1.1rem;
  line-height: 1.8;
  text-align: justify;
  min-height: 200px;
}

@media (max-width: 960px) {
  .page-title {
    font-size: 2.5rem;
  }

  .content-wrapper {
    flex-direction: column;
  }

  .image-container {
    max-width: 100%;
  }

  .text-content {
    order: -1;
    padding: 1rem;
  }

  .description-container {
    padding: 1.5rem;
  }

  .description-text {
    font-size: 1rem;
    min-height: 150px;
  }
}
</style> 