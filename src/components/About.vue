<template>
  <section id="about">
    <div class="section-label">Chi sono</div>
    <div class="about-grid">
      <div class="about-text">
        <p>
          Sono un <strong>sviluppatore full-stack</strong> con una solida base in
          HTML, CSS e JavaScript, sempre alla ricerca di nuove sfide tecniche.
        </p>
        <p>
          Mi appassiona l'intersezione tra <strong>design raffinato</strong> e
          tecnologia funzionale — dalla creazione di blog e portfolio
          al mondo della <strong>blockchain e Web3</strong>.
        </p>
        <p>
          Nel tempo libero esploro lo <strong>sviluppo di videogiochi</strong>
          con DragonRuby e costruisco strumenti per la finanza personale.
        </p>
      </div>
      <div class="skills-grid">
        <div class="skill-item" v-for="skill in skills" :key="skill.name">
          <div class="skill-name">{{ skill.name }}</div>
          <div class="skill-desc">{{ skill.desc }}</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const skills = [
  { name: 'HTML / CSS',   desc: 'Markup semantico e stile raffinato' },
  { name: 'JavaScript',   desc: 'Interattività e logica front-end' },
  { name: 'Vue.js',       desc: 'UI reattive e componenti modulari' },
  { name: 'Blockchain',   desc: 'ERC20, Foundry, Base network' },
  { name: 'DragonRuby',   desc: 'Game dev e prototipazione' },
  { name: 'Design',       desc: 'Tipografia, layout e UX' },
]
</script>

<style scoped>
section {
  padding: 7rem 4rem;
}

.about-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 6rem; align-items: center;
  max-width: 1100px;
}

.about-text p {
  color: var(--muted); font-weight: 300;
  margin-bottom: 1.2rem; font-size: 1.05rem;
}

.about-text p:last-child { margin-bottom: 0 }
.about-text strong { color: var(--text); font-weight: 400 }

.skills-grid {
  display: grid; grid-template-columns: 1fr 1fr; gap: 1rem;
}

.skill-item {
  padding: 1.25rem 1.5rem;
  border: 1px solid var(--border);
  transition: border-color .3s;
}

.skill-item:hover { border-color: var(--border2) }

.skill-name {
  font-family: 'DM Mono', monospace; font-size: .8rem; font-weight: 300;
  color: var(--gold); letter-spacing: .1em; margin-bottom: .3rem;
}

.skill-desc { font-size: .85rem; color: var(--muted2); font-weight: 300 }

@media (max-width: 768px) {
  section { padding: 5rem 1.5rem }
  .about-grid { grid-template-columns: 1fr; gap: 3rem }
}
</style>