<template>
  <section class="career">
    <h2 class="section-title">Mon Parcours</h2>

    <div class="timeline-container">
      <div class="timeline-line"></div>
      
      <div v-for="(item, index) in careerItems" 
           :key="index" 
           class="timeline-item">
        <div class="timeline-dot"></div>
        <div class="timeline-content">
          <h3 class="timeline-date">{{ item.date }}</h3>
          <div class="timeline-card">
            <h4 class="timeline-title">{{ item.title }}</h4>
            <p class="timeline-description">{{ item.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Career',
  data() {
    return {
      careerItems: [
        {
          date: 'Juillet 2023',
          title: 'BAC Général',
          description: 'Mention Assez Bien Spé Maths/NSI'
        },
        {
          date: 'Septembre 2023',
          title: 'Entrée à l\'EPSI',
          description: 'Entrée en 1ère année en cycle développeur'
        },
        {
          date: 'Mai 2024',
          title: 'Stage IRTS',
          description: 'Développement d\'un support de formation en VR'
        },
        {
          date: 'Septembre 2024',
          title: 'Entrée en 2ème année',
          description: 'Cycle développeur'
        },
        {
          date: 'Septembre 2025',
          title: 'Entrée en Bachelor SysOps',
        }
      ]
    }
  }
}
</script>

<style scoped>
.career {
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

.career::before {
  content: none;
}

.section-title, .timeline-container {
  position: relative;
  z-index: 1;
}

.section-title {
  color: var(--pastel-purple);
  font-size: 2.5rem;
  text-align: center;
  margin-bottom: 3rem;
  font-weight: 700;
  letter-spacing: 1px;
  text-shadow: 2px 2px 3px rgba(255, 255, 255, 0.8);
  position: relative;
  display: inline-block;
  transform: none;
  left: 0;
}

.section-title::after {
  content: '';
  display: block;
  width: 80px;
  height: 4px;
  background: linear-gradient(to right, var(--pastel-purple), var(--pastel-teal));
  margin: 0.5rem auto 0;
  border-radius: 2px;
}

.timeline-container {
  max-width: 600px;
  margin: 0 auto;
  position: relative;
  padding: 1rem 0;
}

.timeline-line {
  position: absolute;
  left: 20px;
  width: 4px;
  height: 100%;
  background: linear-gradient(to bottom, var(--pastel-purple), var(--pastel-teal));
  opacity: 0.6;
  border-radius: 2px;
}

.timeline-item {
  display: flex;
  justify-content: flex-start;
  align-items: flex-start;
  margin-bottom: 3.5rem;
  position: relative;
}

.timeline-dot {
  position: absolute;
  left: 20px;
  transform: translateX(-50%);
  width: 24px;
  height: 24px;
  background: linear-gradient(45deg, var(--pastel-purple), var(--pastel-teal));
  border-radius: 50%;
  z-index: 2;
  box-shadow: 0 0 0 4px var(--bg-primary), 
             0 0 0 6px rgba(106, 90, 205, 0.2),
             0 0 20px rgba(106, 90, 205, 0.4);
  transition: all 0.3s ease;
}

.timeline-item:hover .timeline-dot {
  transform: translateX(-50%) scale(1.2);
  box-shadow: 0 0 0 4px var(--bg-primary), 
             0 0 0 6px rgba(106, 90, 205, 0.3),
             0 0 25px rgba(106, 90, 205, 0.5);
}

.timeline-content {
  width: calc(100% - 50px);
  margin-left: 50px;
  position: relative;
}

.timeline-item:nth-child(even) .timeline-content {
  margin-left: 50px;
  margin-right: 0;
  text-align: left;
}

.timeline-date {
  color: var(--pastel-coral);
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
  font-weight: 700;
  text-shadow: 1px 1px 2px rgba(255, 255, 255, 0.8);
}

.timeline-card {
  background: rgba(255, 255, 255, 0.85);
  border-radius: 12px;
  padding: 1.5rem;
  border: 2px solid;
  border-image: linear-gradient(45deg, var(--pastel-purple), var(--pastel-teal)) 1;
  box-shadow: 0 5px 15px rgba(106, 90, 205, 0.2),
              inset 0 0 15px rgba(255, 255, 255, 0.6);
  transition: all 0.3s ease;
}

.timeline-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 25px rgba(106, 90, 205, 0.3),
              inset 0 0 15px rgba(255, 255, 255, 0.6);
}

.timeline-title {
  color: var(--pastel-navy);
  font-size: 1.3rem;
  margin-bottom: 0.8rem;
  font-weight: 700;
}

.timeline-description {
  color: var(--text-dark);
  font-size: 1rem;
  line-height: 1.6;
}

@media (max-width: 768px) {
  .timeline-line {
    left: 20px;
  }
  
  .timeline-dot {
    left: 20px;
  }
  
  .timeline-content {
    width: calc(100% - 50px);
    margin-left: 50px;
  }
  
  .timeline-item:nth-child(even) .timeline-content {
    margin-left: 50px;
    margin-right: 0;
    text-align: left;
  }
}
</style> 