<template>
  <footer>
    <p>© {{ year }} Gabriel S. — Tutti i diritti riservati</p>
    <p>Costruito con Vue.js &amp; amore per il dettaglio</p>
  </footer>
</template>

<script setup>
const year = new Date().getFullYear()
</script>

<style scoped>
footer {
  border-top: 1px solid var(--border);
  padding: 2rem 4rem;
  display: flex; justify-content: space-between; align-items: center;
  flex-wrap: wrap; gap: 1rem;
}

footer p {
  font-family: 'DM Mono', monospace; font-size: .72rem;
  font-weight: 300; color: var(--muted2); letter-spacing: .08em;
}

@media (max-width: 768px) {
  footer { padding: 2rem 1.5rem }
}
</style>