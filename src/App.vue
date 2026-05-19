<script setup>
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Skills from './components/Skills.vue'
import Projects from './components/Projects.vue'
import Contact from './components/Contact.vue'
import ScrollToTop from './components/ScrollToTop.vue'
</script>

<template>
  <div class="app-container">
    <Navbar />
    <main>
      <Hero />
      <About />
      <Skills />
      <Projects />
      <Contact />
    </main>
    <footer class="footer">
      <p>&copy; 2026 Jhon Santana. Todos los derechos reservados.</p>
    </footer>
    <ScrollToTop />
  </div>
</template>

<style scoped>
.app-container {
  min-height: 100vh;
}

.footer {
  text-align: center;
  padding: 2rem;
  color: #64748b;
  border-top: 1px solid rgba(255,255,255,0.05);
  margin-top: 2rem;
}
</style>
