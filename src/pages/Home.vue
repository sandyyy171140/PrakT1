<template>
  <section class="home">
    <div class="content">
      <h1>Hi, I am <span>{{ name }}</span></h1>
      <h2><span ref="typingText"></span><span class="cursor">|</span></h2>
      <p>Saya adalah seorang yang menyukai dunia web development dan desain UI/UX.</p>
      <a href="/cv.pdf" class="btn" download>Download CV</a>
    </div>
  </section>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      name: "Sandy Satria",
      skills: ["Frontend Developer", "UI/UX Designer", "233510014"],
      currentSkillIndex: 0,
      typingInterval: null,
    };
  },
  mounted() {
    this.typeSkill();
  },
  methods: {
    typeSkill() {
      const el = this.$refs.typingText;
      let index = 0;
      const updateText = () => {
        const skill = this.skills[this.currentSkillIndex];
        el.textContent = skill.slice(0, index++);
        if (index > skill.length) {
          clearInterval(this.typingInterval);
          setTimeout(() => {
            this.currentSkillIndex = (this.currentSkillIndex + 1) % this.skills.length;
            index = 0;
            this.typingInterval = setInterval(updateText, 150);
          }, 2000);
        }
      };
      this.typingInterval = setInterval(updateText, 150);
    },
  },
  beforeUnmount() {
    clearInterval(this.typingInterval);
  },
};
</script>

<style scoped>
.home {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: calc(100vh - 80px);
  background: #000;
  color: white;
  text-align: center;
  padding: 2rem;
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
  margin-bottom: 1rem;
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

p {
  font-size: 1rem;
  margin-bottom: 1.5rem;
  max-width: 600px;
  margin-inline: auto;
}

.btn {
  background: cyan;
  color: black;
  padding: 0.75rem 1.5rem;
  text-decoration: none;
  font-weight: bold;
  border-radius: 8px;
  transition: 0.3s;
}

.btn:hover {
  background: white;
}
</style>
