<template>
  <section class="about-me">
    <h2 class="section-title">À propos de moi</h2>

    <div class="content-container">
      <div class="profile-container">
        <img src="/src/assets/image_profile.png" alt="Photo de profil" class="profile-image" />
      </div>

      <div class="description-container">
        <div class="text-box">
          <p>
            Lorem Ipsum is simply dummy text of the printing and typesetting industry. 
            Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, 
            but also the leap into electronic typesetting, remaining essentially unchanged.
          </p>
        </div>

        <div class="text-box">
          <p>
            Lorem Ipsum is simply dummy text of the printing and typesetting industry. 
            Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, 
            but also the leap into electronic typesetting, remaining essentially unchanged.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'AboutMe'
}
</script>

<style scoped>
.about-me {
  min-height: 100vh;
  background: transparent;
  padding: 3rem 2rem;
  position: relative;
  overflow: hidden;
}

.about-me::before {
  content: none;
}

.section-title, .content-container, .profile-container {
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
  left: 50%;
  transform: translateX(-50%);
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

.content-container {
  max-width: 850px;
  margin: 0 auto;
}

.profile-container {
  display: flex;
  justify-content: center;
  margin-bottom: 2.5rem;
}

.profile-image {
  width: 180px;
  height: 180px;
  border-radius: 50%;
  border: 4px solid var(--white);
  box-shadow: 0 8px 25px rgba(106, 90, 205, 0.3),
              0 0 0 8px rgba(106, 90, 205, 0.1);
  object-fit: cover;
  transition: all 0.3s ease;
}

.profile-image:hover {
  transform: scale(1.05);
  border-color: var(--pastel-purple);
  box-shadow: 0 12px 30px rgba(106, 90, 205, 0.4),
              0 0 0 12px rgba(106, 90, 205, 0.15);
}

.description-container {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.text-box {
  padding: 2rem;
  background: rgba(255, 255, 255, 0.85);
  border-radius: 15px;
  border: 2px solid var(--pastel-teal);
  box-shadow: 0 5px 20px rgba(32, 178, 170, 0.2),
              inset 0 0 15px rgba(255, 255, 255, 0.6);
  transition: all 0.3s ease;
}

.text-box:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 25px rgba(32, 178, 170, 0.3),
              inset 0 0 15px rgba(255, 255, 255, 0.6);
}

.text-box p {
  color: var(--text-dark);
  font-size: 1.05rem;
  line-height: 1.7;
}

@media (max-width: 768px) {
  .section-title {
    font-size: 2.2rem;
  }
  
  .profile-image {
    width: 150px;
    height: 150px;
  }
  
  .text-box {
    padding: 1.5rem;
  }
}
</style> 