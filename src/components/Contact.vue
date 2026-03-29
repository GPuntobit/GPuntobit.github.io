<template>
  <section id="contact">
    <div class="contact-inner">
      <div class="section-label">Contatti</div>
      <h2 class="contact-title">
        Costruiamo qualcosa di <em>straordinario</em> insieme.
      </h2>
      <p class="contact-text">
        Hai un progetto in mente o vuoi semplicemente scambiare idee?
        Sono sempre aperto a nuove conversazioni.
      </p>
      <div class="contact-links">
        <a href="mailto:gabriele@example.com" class="contact-link">Email</a>
        <a href="#" class="contact-link">GitHub</a>
        <a href="#" class="contact-link">LinkedIn</a>
      </div>
    </div>
  </section>
</template>

<style scoped>
section { padding: 7rem 4rem }

.contact-inner { max-width: 700px }

.contact-title {
  font-size: clamp(2.5rem, 5vw, 4.5rem);
  font-weight: 300; line-height: 1.1; margin-bottom: 2rem;
}

.contact-title em { font-style: italic; color: var(--gold) }

.contact-text {
  font-size: 1.05rem; color: var(--muted); font-weight: 300;
  margin-bottom: 3rem; max-width: 480px;
}

.contact-links { display: flex; gap: 2rem; flex-wrap: wrap }

.contact-link {
  font-family: 'DM Mono', monospace; font-size: .8rem; font-weight: 300;
  letter-spacing: .15em; text-transform: uppercase;
  color: var(--text); text-decoration: none;
  padding: .8rem 1.5rem; border: 1px solid var(--border2);
  transition: border-color .3s, color .3s;
}

.contact-link:hover { border-color: var(--gold); color: var(--gold) }

@media (max-width: 768px) {
  section { padding: 5rem 1.5rem }
}
</style>