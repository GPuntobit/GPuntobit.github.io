<template>
  <section class="hero" id="home">
    <div class="hero-inner">
      <p class="hero-eyebrow fade-up">Developer &amp; Creator</p>
      <h1 class="hero-title fade-up delay-1">
        Ciao, sono<br><em>Gabriel</em>.
      </h1>
      <p class="hero-sub fade-up delay-2">
        Sviluppatore web con passione per il design elegante,
        la blockchain e le esperienze digitali memorabili.
      </p>
      <a href="#projects" class="hero-cta fade-up delay-3">
        Vedi i progetti <span>→</span>
      </a>
    </div>
    <div class="hero-scroll">Scorri</div>
  </section>
</template>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex; align-items: center;
  padding: 0 4rem;
  position: relative; overflow: hidden;
}

.hero::before {
  content: '';
  position: absolute; top: -20%; right: -10%;
  width: 50vw; height: 80vh;
  background: radial-gradient(ellipse at center, rgba(201,169,110,.06) 0%, transparent 70%);
  pointer-events: none;
}

.hero-inner { max-width: 800px }

.hero-eyebrow {
  font-family: 'DM Mono', monospace;
  font-size: .8rem; font-weight: 300;
  color: var(--gold); letter-spacing: .2em; text-transform: uppercase;
  margin-bottom: 2rem;
  display: flex; align-items: center; gap: 1rem;
}

.hero-eyebrow::before {
  content: ''; display: block;
  width: 40px; height: 1px; background: var(--gold); opacity: .5;
}

.hero-title {
  font-size: clamp(3.5rem, 8vw, 7rem);
  font-weight: 300; line-height: 1.05;
  letter-spacing: -.02em; margin-bottom: 1.5rem;
}

.hero-title em { font-style: italic; color: var(--gold); font-weight: 300 }

.hero-sub {
  font-size: 1.1rem; font-weight: 300;
  color: var(--muted); max-width: 480px;
  margin-bottom: 3rem; line-height: 1.8;
}

.hero-cta {
  display: inline-flex; align-items: center; gap: .75rem;
  font-family: 'DM Mono', monospace; font-size: .8rem; font-weight: 300;
  letter-spacing: .15em; text-transform: uppercase;
  color: var(--text); border: 1px solid var(--border2);
  padding: .9rem 2rem; text-decoration: none;
  transition: border-color .3s, color .3s; cursor: pointer;
}

.hero-cta:hover { border-color: var(--gold); color: var(--gold) }

.hero-scroll {
  position: absolute; bottom: 3rem; left: 4rem;
  font-family: 'DM Mono', monospace; font-size: .7rem; font-weight: 300;
  color: var(--muted2); letter-spacing: .15em; text-transform: uppercase;
  writing-mode: vertical-rl;
  display: flex; align-items: center; gap: 1rem;
}

.hero-scroll::after {
  content: ''; display: block;
  width: 1px; height: 60px; background: var(--border2);
}

@media (max-width: 768px) {
  .hero { padding: 0 1.5rem }
  .hero-scroll { display: none }
}
</style>