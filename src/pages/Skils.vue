<template>
  <section class="skils">
    <h1>Keahlian</h1>
    <div class="grid">
      <div class="card" v-for="(skill, index) in skills" :key="index">
        <h3>{{ skill.name }}</h3>
        <p>{{ skill.level }}</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Skils",
  data() {
    return {
      skills: [
        { name: "HTML & CSS", level: "Lanjutan" },
        { name: "JavaScript", level: "Menengah" },
        { name: "Vue.js", level: "Menengah" },
        { name: "UI/UX Design", level: "Dasar" },
        { name: "Git & GitHub", level: "Menengah" },
      ],
    };
  },
};
</script>

<style scoped>
.skils {
  background: #000;
  color: white;
  padding: 3rem 1rem;
  text-align: center;
}

.skils h1 {
  font-size: 2.5rem;
  color: cyan;
  margin-bottom: 2rem;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1.5rem;
  max-width: 1000px;
  margin: auto;
}

.card {
  background: #111;
  padding: 1.5rem;
  border-radius: 12px;
  border: 1px solid cyan;
  transition: transform 0.3s ease;
}

.card:hover {
  transform: translateY(-5px);
}
</style>
