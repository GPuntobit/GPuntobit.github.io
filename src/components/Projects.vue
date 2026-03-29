<template>
  <section id="projects">
    <div class="section-label">Lavori selezionati</div>
    <div class="projects-grid">
      <div class="project-card" v-for="(project, i) in projects" :key="project.title">
        <div class="project-num">{{ String(i + 1).padStart(2, '0') }}</div>
        <h3 class="project-title">{{ project.title }}</h3>
        <p class="project-desc">{{ project.desc }}</p>
        <div class="project-tags">
          <span class="tag" v-for="tag in project.tags" :key="tag">{{ tag }}</span>
        </div>
        <a href="#" class="project-link">Esplora →</a>
      </div>
    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    title: 'Blog by G.S.',
    desc: 'Blog personale con layout editoriale, navigazione a dropdown e sistema SCSS personalizzato.',
    tags: ['HTML', 'CSS', 'jQuery', 'Font Awesome'],
  },
  {
    title: 'Staking Calculator',
    desc: 'Notebook interattivo per calcoli di compound interest su criptovalute con analisi per scenario.',
    tags: ['Jupyter', 'Finanza'],
  },
  {
    title: 'Token ERC20',
    desc: 'Deploy di un token personalizzato sulla testnet Base Sepolia tramite Foundry e OpenZeppelin.',
    tags: ['Solidity', 'Foundry', 'Base', 'Web3'],
  },
  {
    title: 'Puzzle Game',
    desc: 'Gioco puzzle in stile Sokoban con estetica fantasy, sviluppato in DragonRuby GTK.',
    tags: ['DragonRuby', 'Ruby', 'Game Dev'],
  },
  {
    title: 'Portfolio Template',
    desc: 'Template portfolio con Alpine.js e Tailwind CSS, tema scuro vibrante e sezioni animate.',
    tags: ['Alpine.js', 'Tailwind', 'HTML'],
  },
  {
    title: 'Finance Tracker',
    desc: 'Dashboard per il monitoraggio delle finanze personali con KPI e grafici Plotly interattivi.',
    tags: ['Python', 'Plotly', 'Datalore'],
  },
]
</script>

<style scoped>
section { padding: 7rem 4rem }

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 1.5px;
  background: var(--border);
}

.project-card {
  background: var(--bg);
  padding: 2.5rem;
  cursor: pointer;
  transition: background .3s;
  position: relative; overflow: hidden;
}

.project-card::after {
  content: ''; position: absolute; bottom: 0; left: 0; right: 0;
  height: 2px; background: var(--gold);
  transform: scaleX(0); transform-origin: left;
  transition: transform .4s cubic-bezier(.4,0,.2,1);
}

.project-card:hover { background: var(--bg3) }
.project-card:hover::after { transform: scaleX(1) }

.project-num {
  font-family: 'DM Mono', monospace; font-size: .7rem;
  color: var(--muted2); letter-spacing: .1em; margin-bottom: 1.5rem;
}

.project-title { font-size: 1.5rem; font-weight: 300; margin-bottom: .75rem }

.project-desc {
  font-size: .95rem; color: var(--muted); font-weight: 300;
  margin-bottom: 1.5rem; line-height: 1.7;
}

.project-tags { display: flex; flex-wrap: wrap; gap: .5rem }

.tag {
  font-family: 'DM Mono', monospace; font-size: .7rem; font-weight: 300;
  color: var(--muted2); letter-spacing: .08em;
  border: 1px solid var(--border); padding: .25rem .75rem;
}

.project-link {
  display: inline-flex; align-items: center; gap: .5rem;
  font-family: 'DM Mono', monospace; font-size: .75rem;
  color: var(--gold); text-decoration: none; margin-top: 1.5rem;
  letter-spacing: .1em; text-transform: uppercase;
  transition: gap .25s;
}

.project-link:hover { gap: .75rem }

@media (max-width: 768px) {
  section { padding: 5rem 1.5rem }
}
</style>