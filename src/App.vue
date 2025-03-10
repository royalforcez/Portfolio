<template>
  <div class="app">
    <HomePage />
    <AboutMe />
    <Career />
    <Projects />
    <MarketingProject />
    <ProjectImages />
    <ProjectImages2 />
    <VirtualRealityProject />
    <IRTSGallery />
    <!-- Les autres sections seront ajoutées ici -->
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
    IRTSGallery
  }
}
</script>

<style>
:root {
  --primary-blue: #1e3d59;
  --secondary-blue: #3498db;
  --white: #ffffff;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  font-family: 'Poppins', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style> 