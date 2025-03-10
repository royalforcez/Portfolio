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
  background: linear-gradient(135deg, var(--primary-blue) 0%, #1a2a3d 100%);
  padding: 2rem;
}

.section-title {
  color: var(--white);
  font-size: 2.5rem;
  text-align: center;
  margin-bottom: 2rem;
}

.content-container {
  max-width: 800px;
  margin: 0 auto;
}

.profile-container {
  display: flex;
  justify-content: center;
  margin-bottom: 2rem;
}

.profile-image {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  border: 3px solid var(--white);
}

.description-container {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.text-box {
  padding: 1.5rem;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 10px;
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.text-box p {
  color: var(--white);
  font-size: 1rem;
  line-height: 1.5;
}

@media (max-width: 768px) {
  .section-title {
    font-size: 2rem;
  }
  
  .profile-image {
    width: 120px;
    height: 120px;
  }
}
</style> 