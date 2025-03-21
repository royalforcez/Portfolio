<template>
  <div class="app">
    <div class="animated-background">
      <div class="shape shape-1"></div>
      <div class="shape shape-2"></div>
      <div class="shape shape-3"></div>
      <div class="shape shape-4"></div>
      <div class="shape shape-5"></div>
      <div class="shape shape-6"></div>
    </div>
    <div class="snap-container">
      <section class="snap-section"><HomePage /></section>
      <section class="snap-section"><AboutMe /></section>
      <section class="snap-section scrollable-section"><Career /></section>
      <section class="snap-section"><Projects /></section>
      <section class="snap-section scrollable-section"><MarketingProject /></section>
      <section class="snap-section"><ProjectImages /></section>
      <section class="snap-section"><ProjectImages2 /></section>
      <section class="snap-section"><VirtualRealityProject /></section>
      <section class="snap-section"><IRTSGallery /></section>
      <section class="snap-section scrollable-section"><IRTSDocumentation /></section>
      <section class="snap-section"><WorkshopMinecraft /></section>
      <section class="snap-section"><WorkshopMinecraftGallery /></section>
      <section class="snap-section"><LANProject /></section>
      <section class="snap-section"><LANGallery /></section>
    </div>
  </div>
</template>

<script>
import HomePage from './components/HomePage.vue'
import AboutMe from './components/AboutMe.vue'
import Career from './components/Career.vue'
import Projects from './components/Projects.vue'
import MarketingProject from './components/MarketingProject.vue'
import ProjectImages from './components/ProjectImages.vue'
import ProjectImages2 from './components/ProjectImages2.vue'
import VirtualRealityProject from './components/VirtualRealityProject.vue'
import IRTSGallery from './components/IRTSGallery.vue'
import IRTSDocumentation from './components/IRTSDocumentation.vue'
import WorkshopMinecraft from './components/WorkshopMinecraft.vue'
import WorkshopMinecraftGallery from './components/WorkshopMinecraftGallery.vue'
import LANProject from './components/LANProject.vue'
import LANGallery from './components/LANGallery.vue'

export default {
  name: 'App',
  components: {
    HomePage,
    AboutMe,
    Career,
    Projects,
    MarketingProject,
    ProjectImages,
    ProjectImages2,
    VirtualRealityProject,
    IRTSGallery,
    IRTSDocumentation,
    WorkshopMinecraft,
    WorkshopMinecraftGallery,
    LANProject,
    LANGallery
  },
  mounted() {
    // Gestion du défilement améliorée
    document.querySelectorAll('.scrollable-section').forEach(section => {
      section.addEventListener('wheel', (event) => {
        const { deltaY } = event;
        const contentHeight = section.scrollHeight;
        const visibleHeight = section.clientHeight;
        const scrollTop = section.scrollTop;
        
        // Si on défile vers le bas et qu'on n'est pas en bas de la section
        if (deltaY > 0 && scrollTop + visibleHeight < contentHeight) {
          event.stopPropagation();
        } 
        // Si on défile vers le haut et qu'on n'est pas en haut de la section
        else if (deltaY < 0 && scrollTop > 0) {
          event.stopPropagation();
        }
      }, { passive: false });
    });
  }
}
</script>

<style>
:root {
  /* Nouvelles couleurs de fond pastel vibrant */
  --bg-primary: #fef0ff;       /* Fond rose très pâle */
  --bg-secondary: #f5f0ff;     /* Fond lavande très pâle */
  --bg-accent: #e6faff;        /* Fond bleu ciel très pâle */
  
  /* Couleur de fond pastel pour toutes les pages */
  --page-bg: #f9f0ff;          /* Fond lavande très pâle uniforme */
  --page-bg-alt: #f8f5ff;      /* Variante légèrement plus claire pour animations */
  
  /* Couleurs principales pastel vives avec bon contraste */
  --pastel-navy: #6a5acd;      /* Violet vibrant (slate blue) - contraste ~7:1 sur fond pâle */
  --pastel-teal: #20b2aa;      /* Turquoise vif - contraste ~7:1 sur fond pâle */
  --pastel-purple: #9370db;    /* Violet moyen vif - contraste ~7:1 sur fond pâle */
  
  /* Couleurs d'accent pastel flashy */
  --pastel-coral: #ff6b88;     /* Rose corail vif - contraste ~7:1 sur fond pâle */
  --pastel-mint: #3cb371;      /* Vert menthe vif - contraste ~7:1 sur fond pâle */
  --pastel-gold: #ffa343;      /* Orange pêche vif - contraste ~7:1 sur fond pâle */
  
  /* Couleurs de texte */
  --text-dark: #352c63;        /* Violet foncé pour texte principal - contraste 12:1+ sur fond pâle */
  --text-medium: #5d4c95;      /* Violet moyen pour texte secondaire - contraste 7.5:1+ sur fond pâle */
  
  /* Couleurs pour bordures et lignes */
  --border-light: #dcd0ff;     /* Lavande pâle pour bordures légères */
  --border-medium: #b8a2f2;    /* Lavande moyen pour bordures plus visibles */
  
  /* Couleurs pour état des éléments interactifs */
  --hover-teal: #17d8ce;       /* Version plus vive de teal pour hover */
  --active-navy: #5147a7;      /* Version plus foncée de navy pour état actif */
  
  /* Conserver le blanc pour certains éléments */
  --white: #ffffff;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html, body {
  height: 100%;
  overflow: hidden;
}

.app {
  font-family: 'Poppins', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100vh;
  overflow: hidden;
  color: var(--text-dark);
  position: relative;
}

.animated-background {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
  background: linear-gradient(135deg, var(--bg-primary) 0%, var(--bg-secondary) 100%);
  background-size: 400% 400%;
  animation: gradient-shift 15s ease infinite;
}

@keyframes gradient-shift {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

.shape {
  position: absolute;
  backdrop-filter: blur(8px);
  border-radius: 50%;
  animation-timing-function: cubic-bezier(0.45, 0.05, 0.55, 0.95);
  animation-iteration-count: infinite;
  animation-direction: alternate;
  opacity: 0.65;
}

.shape-1 {
  width: 300px;
  height: 300px;
  background: radial-gradient(circle at 30% 40%, rgba(147, 112, 219, 0.25), rgba(106, 90, 205, 0.15));
  top: 10%;
  left: 10%;
  animation: float-1 15s infinite;
}

.shape-2 {
  width: 250px;
  height: 250px;
  background: radial-gradient(circle at 30% 40%, rgba(32, 178, 170, 0.2), rgba(60, 179, 113, 0.15));
  top: 60%;
  left: 20%;
  animation: float-2 18s infinite;
}

.shape-3 {
  width: 450px;
  height: 450px;
  background: radial-gradient(circle at 30% 40%, rgba(255, 107, 136, 0.15), rgba(255, 163, 67, 0.1));
  bottom: -10%;
  right: 10%;
  animation: float-3 20s infinite;
}

.shape-4 {
  width: 180px;
  height: 180px;
  background: radial-gradient(circle at 30% 40%, rgba(147, 112, 219, 0.2), rgba(106, 90, 205, 0.12));
  top: 25%;
  right: 25%;
  animation: float-4 14s infinite;
}

.shape-5 {
  width: 220px;
  height: 220px;
  background: radial-gradient(circle at 30% 40%, rgba(32, 178, 170, 0.18), rgba(60, 179, 113, 0.12));
  top: 70%;
  right: 40%;
  animation: float-5 16s infinite;
}

.shape-6 {
  width: 320px;
  height: 320px;
  background: radial-gradient(circle at 30% 40%, rgba(255, 107, 136, 0.12), rgba(255, 163, 67, 0.08));
  top: 35%;
  left: 48%;
  animation: float-6 22s infinite;
}

@keyframes float-1 {
  0% {
    transform: translate(0, 0) rotate(0deg) scale(1);
  }
  50% {
    transform: translate(80px, 40px) rotate(8deg) scale(1.08);
  }
  100% {
    transform: translate(-60px, 50px) rotate(-5deg) scale(0.95);
  }
}

@keyframes float-2 {
  0% {
    transform: translate(0, 0) rotate(0deg) scale(1);
  }
  50% {
    transform: translate(-50px, 70px) rotate(-12deg) scale(1.15);
  }
  100% {
    transform: translate(40px, -40px) rotate(6deg) scale(0.92);
  }
}

@keyframes float-3 {
  0% {
    transform: translate(0, 0) rotate(0deg) scale(1);
  }
  50% {
    transform: translate(-60px, -60px) rotate(5deg) scale(0.9);
  }
  100% {
    transform: translate(40px, 50px) rotate(-7deg) scale(1.06);
  }
}

@keyframes float-4 {
  0% {
    transform: translate(0, 0) rotate(0deg) scale(1);
  }
  50% {
    transform: translate(40px, -40px) rotate(-8deg) scale(1.12);
  }
  100% {
    transform: translate(-30px, 30px) rotate(10deg) scale(0.94);
  }
}

@keyframes float-5 {
  0% {
    transform: translate(0, 0) rotate(0deg) scale(1);
  }
  50% {
    transform: translate(60px, 20px) rotate(10deg) scale(0.88);
  }
  100% {
    transform: translate(-50px, -25px) rotate(-15deg) scale(1.1);
  }
}

@keyframes float-6 {
  0% {
    transform: translate(0, 0) rotate(0deg) scale(1);
  }
  50% {
    transform: translate(-40px, 40px) rotate(-6deg) scale(1.06);
  }
  100% {
    transform: translate(30px, -50px) rotate(8deg) scale(0.92);
  }
}

.snap-container {
  height: 100vh;
  overflow-y: scroll;
  scroll-snap-type: y mandatory;
  scroll-behavior: smooth;
  position: relative;
  z-index: 1;
}

.snap-section {
  scroll-snap-align: start;
  height: 100vh;
  width: 100%;
  position: relative;
}

.scrollable-section {
  overflow-y: auto;
  overflow-x: hidden;
}

.snap-section:not(.scrollable-section) {
  overflow: hidden;
}

/* Afficher la barre de défilement pour les sections scrollables */
.scrollable-section::-webkit-scrollbar {
  width: 5px;
}

.scrollable-section::-webkit-scrollbar-track {
  background: var(--border-light);
}

.scrollable-section::-webkit-scrollbar-thumb {
  background: var(--pastel-navy);
  border-radius: 10px;
}

/* Cacher la barre de défilement principale */
.snap-container::-webkit-scrollbar {
  width: 0;
  height: 0;
}
</style> 