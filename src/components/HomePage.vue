<template>
  <section class="home-page">
    <div class="title-container">
      <h1 class="title">Portfolio</h1>
    </div>

    <div class="scroll-indicator">
      <span class="scroll-text">Découvrir</span>
      <div class="scroll-arrow"></div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'HomePage'
}
</script>

<style scoped>
.home-page {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(135deg, var(--primary-blue) 0%, #1a2a3d 100%);
  position: relative;
}

.title-container {
  padding: 2rem 3rem;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 10px;
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.title {
  font-size: 3.5rem;
  color: var(--white);
  letter-spacing: 2px;
  text-align: center;
}

.scroll-indicator {
  position: absolute;
  bottom: 2rem;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.scroll-text {
  color: var(--white);
  font-size: 0.9rem;
  margin-bottom: 0.5rem;
  letter-spacing: 1px;
}

.scroll-arrow {
  width: 15px;
  height: 15px;
  border-right: 2px solid var(--secondary-blue);
  border-bottom: 2px solid var(--secondary-blue);
  transform: rotate(45deg);
}

@media (max-width: 768px) {
  .title {
    font-size: 2.5rem;
  }
  
  .title-container {
    padding: 1.5rem 2rem;
  }
}
</style> 