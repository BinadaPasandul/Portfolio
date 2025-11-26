<script setup lang="ts">
import Navigation from './components/Navigation.vue'
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Skills from './components/Skills.vue'
import Projects from './components/Projects.vue'
import Contact from './components/Contact.vue'
</script>

<template>
  <div class="app">
    <Navigation />
    <Hero />
    <About />
    <Skills />
    <Projects />
    <Contact />
    <footer class="footer">
      <p>&copy; {{ new Date().getFullYear() }} Portfolio. Built with Vue.js</p>
    </footer>
  </div>
</template>

<style scoped>
.app {
  position: relative;
}

.footer {
  background: #0f0c29;
  padding: 2rem;
  text-align: center;
  color: #b0b0b0;
  border-top: 1px solid rgba(102, 126, 234, 0.2);
}

.footer p {
  margin: 0;
}
</style>
