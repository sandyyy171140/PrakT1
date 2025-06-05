<template>
  <nav class="navbar">
    <div class="logo">Portofolio</div>
    <div class="nav-links" :class="{ active: menuOpen }">
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
      <router-link to="/skils">Skils</router-link>
      <router-link to="/contact">Contact</router-link>
    </div>
    <div class="hamburger" v-if="!menuOpen" @click="toggleMenu">&#9776;</div>
    <div class="cancel" v-if="menuOpen" @click="toggleMenu">&times;</div>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      menuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.menuOpen = !this.menuOpen;
    },
  },
};
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: black;
  padding: 1rem 2rem;
  color: white;
  position: sticky;
  top: 0;
  z-index: 100;
}

.logo {
  font-size: 24px;
  font-weight: bold;
}

.nav-links {
  display: flex;
  gap: 1.5rem;
}

.nav-links a {
  color: white;
  text-decoration: none;
  font-weight: 500;
  transition: 0.3s;
}

.nav-links a:hover {
  color: cyan;
}

.hamburger,
.cancel {
  display: none;
  font-size: 30px;
  cursor: pointer;
}

@media (max-width: 768px) {
  .nav-links {
    position: absolute;
    right: 0;
    top: 60px;
    background-color: #111;
    flex-direction: column;
    padding: 1rem;
    gap: 1rem;
    transform: translateX(100%);
    transition: transform 0.3s ease-in-out;
  }

  .nav-links.active {
    transform: translateX(0);
  }

  .hamburger,
  .cancel {
    display: block;
  }
}
</style>
