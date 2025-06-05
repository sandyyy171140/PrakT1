<template>
  <section class="about">
    <div class="content">
      <h1>Tentang <span>Saya</span></h1>
      <h2><span class="role">Full Stack Developer</span><span class="cursor">|</span></h2>
      
      <div class="profile-container">
        <img src="../assets/foto.jpg" alt="Foto Profil" class="profile-img">
        <div class="description">
          <p>Halo! Saya Sandy Satria, seorang Full Stack Developer dengan spesialisasi dalam ekosistem JavaScript.</p>
          <p>Saya memiliki pengalaman dalam membangun aplikasi web modern menggunakan Vue.js, React, dan Node.js.</p>
          <p>Saya percaya bahwa desain dan fungsionalitas harus berjalan seiring untuk menciptakan pengalaman pengguna yang luar biasa.</p>
        </div>
      </div>
      
     
    </div>
  </section>
</template>

<script>
export default {
  name: "About",
}
</script>

<style scoped>
.about {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: calc(100vh - 80px);
  background: #000;
  color: white;
  text-align: center;
  padding: 2rem;
}

.content {
  max-width: 1200px;
  width: 100%;
}

.content h1 {
  font-size: 2.5rem;
  margin-bottom: 0.5rem;
}

.content h1 span {
  color: cyan;
}

.content h2 {
  font-size: 1.5rem;
  margin-bottom: 2rem;
}

.role {
  color: cyan;
}

.cursor {
  display: inline-block;
  animation: blink 1s infinite;
}

@keyframes blink {
  0%, 50%, 100% {
    opacity: 1;
  }
  25%, 75% {
    opacity: 0;
  }
}

.profile-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2rem;
  margin-bottom: 2rem;
}

.profile-img {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  object-fit: cover;
  border: 3px solid cyan;
  box-shadow: 0 0 20px cyan;
}

.description {
  max-width: 600px;
  text-align: left;
}

.description p {
  font-size: 1rem;
  margin-bottom: 1rem;
  line-height: 1.6;
}

.btn {
  background: cyan;
  color: black;
  padding: 0.75rem 1.5rem;
  text-decoration: none;
  font-weight: bold;
  border-radius: 8px;
  transition: 0.3s;
  display: inline-block;
  margin-top: 1rem;
}

.btn:hover {
  background: white;
  transform: scale(1.05);
  box-shadow: 0 0 15px cyan;
}

@media (max-width: 768px) {
  .profile-container {
    flex-direction: column;
  }
  
  .profile-img {
    width: 150px;
    height: 150px;
  }
  
  .description {
    text-align: center;
  }
}
</style>