<template>
  <section class="home-page">
    <div class="title-container">
      <h1 class="title">Sacha</h1> 
      <h2 class="title2">Cazin--Lepczynski</h2>
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
  background: transparent;
  position: relative;
  overflow: hidden;
}

.home-page::before {
  content: none;
}

.title-container {
  padding: 2.5rem 4rem;
  background: rgba(255, 255, 255, 0.85);
  border-radius: 15px;
  border: 3px solid var(--pastel-purple);
  box-shadow: 0 8px 30px rgba(106, 90, 205, 0.3), 
              0 0 0 5px rgba(106, 90, 205, 0.1),
              inset 0 0 15px rgba(255, 255, 255, 0.8);
  transition: all 0.3s ease;
  position: relative;
  z-index: 1;
}

.title-container:hover {
  transform: translateY(-5px);
  box-shadow: 0 12px 40px rgba(106, 90, 205, 0.4), 
              0 0 0 6px rgba(106, 90, 205, 0.15),
              inset 0 0 15px rgba(255, 255, 255, 0.8);
}

.title {
  font-size: 3.8rem;
  background: linear-gradient(45deg, var(--pastel-purple) 20%, var(--pastel-teal) 80%);
  background-clip: text;
  -webkit-background-clip: text;
  color: transparent;
  letter-spacing: 2px;
  text-align: center;
  font-weight: 700;
  text-shadow: 0 2px 10px rgba(255, 255, 255, 0.5);
}

.title2 {
  font-size: 2.0rem;
  background: linear-gradient(45deg, var(--pastel-purple) 20%, var(--pastel-teal) 80%);
  background-clip: text;
  -webkit-background-clip: text;
  color: transparent;
  letter-spacing: 2px;
  text-align: center;
  font-weight: 700;
  text-shadow: 0 2px 10px rgba(255, 255, 255, 0.5);
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
  color: var(--pastel-purple);
  font-size: 1.1rem;
  margin-bottom: 0.8rem;
  letter-spacing: 1px;
  font-weight: 600;
  text-shadow: 0 0 10px rgba(255, 255, 255, 0.8);
}

.scroll-arrow {
  width: 15px;
  height: 15px;
  border-right: 3px solid var(--pastel-purple);
  border-bottom: 3px solid var(--pastel-purple);
  transform: rotate(45deg);
  animation: bounce 1.5s infinite;
  box-shadow: 2px 2px 0 rgba(255, 255, 255, 0.5);
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {
    transform: translateY(0) rotate(45deg);
  }
  40% {
    transform: translateY(-10px) rotate(45deg);
  }
  60% {
    transform: translateY(-5px) rotate(45deg);
  }
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