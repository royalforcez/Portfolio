<template>
  <section class="contact">
    <h2 class="section-title">Contact</h2>

    <div class="content-container">
      <div class="image-container">
        <img src="/src/assets/contact_image.png" alt="Image de contact" class="contact-image" />
      </div>

      <div class="contact-info">
        <div class="contact-item">
          <i class="fas fa-envelope"></i>
          <a href="mailto:votre.email@example.com">cazin.lep@gmail.com</a>
        </div>
        <div class="contact-item">
          <i class="fas fa-phone"></i>
          <a href="tel:+33600000000">06 71 46 15 30</a>
        </div>
        <div class="contact-item">
          <i class="fab fa-linkedin"></i>
          <a href="https://www.linkedin.com/in/sacha-cazin-lepczynski-849443288/" target="_blank">LinkedIn</a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Contact'
}
</script>

<style scoped>
.contact {
  min-height: 100vh;
  background: transparent;
  padding: 3rem 2rem;
  position: relative;
  overflow: hidden;
}

.section-title {
  font-size: 2.5rem;
  color: #333;
  margin-bottom: 2rem;
  text-align: center;
}

.content-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.image-container {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.contact-image {
  max-width: 100%;
  height: auto;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.contact-info {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1rem;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 8px;
  transition: transform 0.3s ease;
}

.contact-item:hover {
  transform: translateX(10px);
}

.contact-item i {
  font-size: 1.5rem;
  color: #333;
}

.contact-item a {
  color: #333;
  text-decoration: none;
  font-size: 1.2rem;
  transition: color 0.3s ease;
}

.contact-item a:hover {
  color: #007bff;
}

@media (max-width: 768px) {
  .content-container {
    flex-direction: column;
  }
  
  .contact-info {
    width: 100%;
  }
}
</style> 