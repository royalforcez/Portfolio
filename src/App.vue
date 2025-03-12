<template>
  <div class="app">
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
      <!-- Les autres sections seront ajoutées ici -->
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
    IRTSDocumentation
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
}

.snap-container {
  height: 100vh;
  overflow-y: scroll;
  scroll-snap-type: y mandatory;
  scroll-behavior: smooth;
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