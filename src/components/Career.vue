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
          date: '2023',
          title: 'Formation 1',
          description: 'Description'
        },
        {
          date: '2022',
          title: 'Formation 2',
          description: 'Description'
        },
        {
          date: '2021',
          title: 'Formation 3',
          description: 'Description'
        },
        {
          date: '2020',
          title: 'Formation 4',
          description: 'Description'
        },
        {
          date: '2019',
          title: 'Formation 5',
          description: 'Description'
        }
      ]
    }
  }
}
</script>

<style scoped>
.career {
  min-height: 100vh;
  background: linear-gradient(135deg, var(--primary-blue) 0%, #1a2a3d 100%);
  padding: 2rem;
}

.section-title {
  color: var(--white);
  font-size: 2.5rem;
  text-align: center;
  margin-bottom: 3rem;
}

.timeline-container {
  max-width: 800px;
  margin: 0 auto;
  position: relative;
  padding: 1rem 0;
}

.timeline-line {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  width: 2px;
  height: 100%;
  background: var(--secondary-blue);
  opacity: 0.5;
}

.timeline-item {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  margin-bottom: 3rem;
  position: relative;
}

.timeline-dot {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  width: 16px;
  height: 16px;
  background: var(--secondary-blue);
  border-radius: 50%;
  z-index: 2;
}

.timeline-content {
  width: 45%;
  margin-left: 55%;
  position: relative;
}

.timeline-item:nth-child(even) .timeline-content {
  margin-left: 0;
  margin-right: 55%;
  text-align: right;
}

.timeline-date {
  color: var(--secondary-blue);
  font-size: 1.1rem;
  margin-bottom: 0.5rem;
  font-weight: 500;
}

.timeline-card {
  background: rgba(255, 255, 255, 0.1);
  border-radius: 10px;
  padding: 1.5rem;
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.timeline-title {
  color: var(--white);
  font-size: 1.2rem;
  margin-bottom: 0.8rem;
}

.timeline-description {
  color: var(--white);
  font-size: 1rem;
  line-height: 1.5;
  opacity: 0.9;
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