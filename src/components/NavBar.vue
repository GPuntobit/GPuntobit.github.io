<template>
  <nav>
    <a href="#" class="nav-logo">G.S.</a>
    <ul class="nav-links" :class="{ open: menuOpen }">
      <li><a href="#about"    @click="menuOpen = false" :class="{ active: active === 'about' }">About</a></li>
      <li><a href="#projects" @click="menuOpen = false" :class="{ active: active === 'projects' }">Progetti</a></li>
      <li><a href="#contact"  @click="menuOpen = false" :class="{ active: active === 'contact' }">Contatti</a></li>
    </ul>
    <div class="nav-ham" @click="menuOpen = !menuOpen" aria-label="Menu">
      <span :style="menuOpen ? 'transform:rotate(45deg) translate(4px,4px)' : ''"></span>
      <span :style="menuOpen ? 'opacity:0' : ''"></span>
      <span :style="menuOpen ? 'transform:rotate(-45deg) translate(4px,-4px)' : ''"></span>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue'

defineProps({
  active: { type: String, default: '' }
})

const menuOpen = ref(false)
</script>

<style scoped>
nav {
  position: fixed; top: 0; left: 0; right: 0; z-index: 100;
  display: flex; align-items: center; justify-content: space-between;
  padding: 1.5rem 4rem;
  background: rgba(10,10,9,0.85);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid var(--border);
}

.nav-logo {
  font-size: 1.1rem;
  font-family: 'DM Mono', monospace;
  font-weight: 300;
  color: var(--gold);
  letter-spacing: .15em;
  text-decoration: none;
}

.nav-links {
  display: flex; gap: 2.5rem; list-style: none;
}

.nav-links a {
  font-size: .85rem;
  font-family: 'DM Mono', monospace;
  font-weight: 300;
  color: var(--muted);
  text-decoration: none;
  letter-spacing: .12em;
  text-transform: uppercase;
  transition: color .25s;
}

.nav-links a:hover,
.nav-links a.active { color: var(--gold) }

.nav-ham {
  display: none; flex-direction: column; gap: 5px;
  cursor: pointer; padding: 4px;
}

.nav-ham span {
  display: block; width: 22px; height: 1px;
  background: var(--muted); transition: .3s;
}

@media (max-width: 768px) {
  nav { padding: 1.25rem 1.5rem }
  .nav-ham { display: flex }
  .nav-links { display: none }
  .nav-links.open {
    display: flex; flex-direction: column; gap: 0;
    position: fixed; top: 65px; left: 0; right: 0; bottom: 0;
    background: var(--bg); padding: 3rem 2rem;
    border-top: 1px solid var(--border);
  }
  .nav-links.open a {
    font-size: 1.2rem; padding: 1rem 0;
    border-bottom: 1px solid var(--border);
  }
}
</style>