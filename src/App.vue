<template>
  <NavBar :active="activeSection" />
  <main>
    <Hero />
    <div class="divider"></div>
    <About />
    <div class="divider"></div>
    <Projects />
    <div class="divider"></div>
    <Contact />
  </main>
  <Footer />
</template>
 
<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import NavBar from './components/NavBar.vue'
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Projects from './components/Projects.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'
 
const activeSection = ref('')
 
function onScroll() {
  const sections = ['about', 'projects', 'contact']
  for (const id of sections) {
    const el = document.getElementById(id)
    if (el) {
      const rect = el.getBoundingClientRect()
      if (rect.top <= 120 && rect.bottom > 120) {
        activeSection.value = id
        return
      }
    }
  }
  activeSection.value = ''
}
 
onMounted(() => window.addEventListener('scroll', onScroll, { passive: true }))
onUnmounted(() => window.removeEventListener('scroll', onScroll))
</script>
 