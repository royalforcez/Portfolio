<template>
  <section class="irts-documentation">
    <h1 class="page-title">Documentation</h1>
    
    <div class="documentation-container">
      
      <div class="doc-section" :class="{ 'active': isCsharpOpen }">
        <div class="section-header" @click="toggleCsharp">
          <h2 class="section-title">Le C#</h2>
          <div class="arrow" :class="{ 'rotated': isCsharpOpen }"></div>
        </div>
        <div class="section-content" :class="{ 'expanded': isCsharpOpen }">
          <div class="content-box">
            
            <p>Description</p>
          </div>
        </div>
      </div>
      
      
      <div class="doc-section" :class="{ 'active': isUnityOpen }">
        <div class="section-header" @click="toggleUnity">
          <h2 class="section-title">Unity</h2>
          <div class="arrow" :class="{ 'rotated': isUnityOpen }"></div>
        </div>
        <div class="section-content" :class="{ 'expanded': isUnityOpen }">
          <div class="content-box">
            
            <p>Description</p>
          </div>
        </div>
      </div>
      
      
      <div class="doc-section" :class="{ 'active': isVarjoOpen }">
        <div class="section-header" @click="toggleVarjo">
          <h2 class="section-title">Varjo/Meta Quest Setup</h2>
          <div class="arrow" :class="{ 'rotated': isVarjoOpen }"></div>
        </div>
        <div class="section-content" :class="{ 'expanded': isVarjoOpen }">
          <div class="content-box">
            
            <p>Description</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'IRTSDocumentation',
  data() {
    return {
      isCsharpOpen: false,
      isUnityOpen: false,
      isVarjoOpen: false
    }
  },
  methods: {
    toggleCsharp() {
      this.isCsharpOpen = !this.isCsharpOpen
      this.isUnityOpen = false
      this.isVarjoOpen = false
    },
    toggleUnity() {
      this.isUnityOpen = !this.isUnityOpen
      this.isCsharpOpen = false
      this.isVarjoOpen = false
    },
    toggleVarjo() {
      this.isVarjoOpen = !this.isVarjoOpen
      this.isCsharpOpen = false
      this.isUnityOpen = false
    }
  }
}
</script>

<style scoped>
.irts-documentation {
  min-height: 100vh;
  background: transparent;
  padding: 3rem 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  overflow: hidden;
}

.irts-documentation::before {
  content: none;
}

.page-title, .documentation-container {
  position: relative;
  z-index: 1;
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

.documentation-container {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 2.5rem;
  max-width: 1200px;
  width: 100%;
}

.doc-section {
  flex: 1;
  min-width: 320px;
  display: flex;
  flex-direction: column;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.doc-section.active {
  transform: translateY(-8px);
}

.section-header {
  padding: 1.5rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  cursor: pointer;
  border-radius: 15px;
  border: 2px solid transparent;
  background-clip: padding-box;
  position: relative;
  z-index: 1;
  background: rgba(255, 255, 255, 0.85);
  transition: all 0.3s ease;
  box-shadow: 0 6px 20px rgba(106, 90, 205, 0.2),
              inset 0 0 15px rgba(255, 255, 255, 0.6);
}

.section-header::before {
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
  opacity: 0.6;
  transition: opacity 0.3s ease;
}

.doc-section.active .section-header {
  border-radius: 15px 15px 0 0;
}

.doc-section.active .section-header::before {
  border-radius: 17px 17px 0 0;
  opacity: 1;
}

.section-header:hover::before {
  opacity: 0.8;
}

.section-title {
  color: var(--pastel-navy);
  font-size: 1.4rem;
  margin: 0;
  font-weight: 700;
}

.arrow {
  width: 12px;
  height: 12px;
  border-right: 2px solid var(--pastel-navy);
  border-bottom: 2px solid var(--pastel-navy);
  transform: rotate(45deg);
  transition: transform 0.3s ease;
}

.arrow.rotated {
  transform: rotate(-135deg);
}

.section-content {
  max-height: 0;
  overflow: hidden;
  transition: all 0.3s ease-in-out;
  opacity: 0;
}

.section-content.expanded {
  max-height: 500px;
  opacity: 1;
}

.content-box {
  padding: 1.8rem;
  border-radius: 0 0 15px 15px;
  border: 2px solid transparent;
  background-clip: padding-box;
  position: relative;
  z-index: 1;
  background: rgba(255, 255, 255, 0.85);
  box-shadow: 0 6px 20px rgba(106, 90, 205, 0.2),
              inset 0 0 15px rgba(255, 255, 255, 0.6);
}

.content-box::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: -1;
  margin: -2px;
  border-radius: 0 0 17px 17px;
  background: linear-gradient(45deg, var(--pastel-purple), var(--pastel-teal));
  opacity: 0.6;
}

.content-box p {
  color: var(--text-dark);
  margin: 0;
  font-size: 1rem;
  line-height: 1.7;
  position: relative;
  z-index: 1;
}

@media (max-width: 960px) {
  .documentation-container {
    flex-direction: column;
    align-items: center;
  }
  
  .doc-section {
    width: 100%;
  }
  
  .page-title {
    font-size: 2.5rem;
  }
  
  .section-title {
    font-size: 1.3rem;
  }
}
</style> 