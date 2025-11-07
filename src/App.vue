<script setup lang="ts">
const navLinks = [
  { label: "Features", href: "#features" },
  { label: "Pricing", href: "#pricing" },
  { label: "Contact", href: "#contact" },
];

const currentYear = new Date().getFullYear();
</script>

<template>
  <div class="page">
    <header class="top-nav">
      <a class="brand" href="#top">Tuthmosis</a>
      <nav class="nav-links">
        <a
          v-for="link in navLinks"
          :key="link.label"
          class="nav-link"
          :href="link.href"
        >
          {{ link.label }}
        </a>
      </nav>
      <a class="nav-cta" href="#contact">Get Started</a>
    </header>

    <main id="top">
      <section class="hero" aria-labelledby="hero-title">
        <div class="hero-copy">
          <p class="eyebrow">Modern data governance</p>
          <h1 id="hero-title">Control your data with confidence</h1>
          <p class="hero-subtitle">
            Tuthmosis gives your team a clear view into pipelines, permissions, and
            policy—so you can deliver trustworthy analytics without delay.
          </p>
          <div class="hero-actions">
            <a class="btn btn-primary" href="#contact">Book a demo</a>
            <a class="btn btn-ghost" href="#features">View features</a>
          </div>
        </div>
        <div class="hero-media" role="presentation">
          <img
            src="https://images.unsplash.com/photo-1545239351-1141bd82e8a6?auto=format&fit=crop&w=1200&q=80"
            alt="Team collaborating on analytics dashboards"
          />
        </div>
      </section>

      <section id="features" class="feature-strip">
        <article>
          <h2>Real-time lineage</h2>
          <p>Visualize every data hop to troubleshoot issues long before they reach production.</p>
        </article>
        <article>
          <h2>Granular controls</h2>
          <p>Grant access with precision using automated policies that scale with your teams.</p>
        </article>
        <article>
          <h2>Unified auditing</h2>
          <p>Audit every change, query, and deployment to stay compliant without the paperwork.</p>
        </article>
      </section>

      <section id="pricing" class="cta-panel">
        <div class="cta-card">
          <h2>Flexible plans for every stage</h2>
          <p>
            Start with our free tier or tailor an enterprise plan with dedicated support and regional
            compliance options.
          </p>
          <a class="btn btn-primary" href="#contact">Talk to sales</a>
        </div>
      </section>
    </main>

    <footer id="contact" class="site-footer">
      <div>
        <strong>Tuthmosis</strong>
        <p>Reach us at <a href="mailto:hello@tuthmosis.io">hello@tuthmosis.io</a></p>
      </div>
      <p>&copy; {{ currentYear }} Tuthmosis Labs. All rights reserved.</p>
    </footer>
  </div>
</template>

<style scoped>
.page {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.top-nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1.25rem 6vw;
  background: rgba(255, 255, 255, 0.8);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(15, 23, 42, 0.08);
  position: sticky;
  top: 0;
  z-index: 10;
}

.brand {
  font-size: 1.25rem;
  font-weight: 700;
  letter-spacing: 0.02em;
}

.nav-links {
  display: flex;
  gap: 1.5rem;
}

.nav-link {
  font-weight: 500;
  opacity: 0.8;
}

.nav-link:hover,
.nav-link:focus {
  opacity: 1;
}

.nav-cta {
  font-weight: 600;
  padding: 0.5rem 1.25rem;
  border-radius: 9999px;
  background: #4f46e5;
  color: #fff;
  box-shadow: 0 10px 30px rgba(79, 70, 229, 0.3);
}

.nav-cta:hover,
.nav-cta:focus {
  background: #4338ca;
}

main {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 6rem;
  padding: 3rem 6vw 4rem;
}

.hero {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  align-items: center;
  gap: 3rem;
}

.hero-copy {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.eyebrow {
  text-transform: uppercase;
  font-size: 0.75rem;
  letter-spacing: 0.2em;
  color: #6366f1;
  font-weight: 600;
}

.hero h1 {
  font-size: clamp(2.5rem, 3.5vw + 1rem, 3.75rem);
  line-height: 1.05;
  margin: 0;
}

.hero-subtitle {
  font-size: 1.05rem;
  color: rgba(15, 23, 42, 0.75);
  max-width: 36ch;
}

.hero-actions {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 0.75rem 1.75rem;
  border-radius: 9999px;
  font-weight: 600;
  transition: transform 0.2s ease, box-shadow 0.2s ease, background-color 0.2s ease,
    color 0.2s ease;
}

.btn-primary {
  background: #4f46e5;
  color: #fff;
  box-shadow: 0 20px 35px rgba(79, 70, 229, 0.25);
}

.btn-primary:hover,
.btn-primary:focus {
  background: #4338ca;
  transform: translateY(-1px);
}

.btn-ghost {
  background: rgba(255, 255, 255, 0.65);
  color: #312e81;
  border: 1px solid rgba(99, 102, 241, 0.4);
}

.btn-ghost:hover,
.btn-ghost:focus {
  background: rgba(99, 102, 241, 0.15);
  transform: translateY(-1px);
}

.hero-media {
  width: 100%;
  border-radius: 28px;
  overflow: hidden;
  box-shadow: 0 40px 70px rgba(15, 23, 42, 0.2);
}

.hero-media img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.feature-strip {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 1.5rem;
}

.feature-strip article {
  background: rgba(255, 255, 255, 0.85);
  border-radius: 20px;
  padding: 2rem;
  box-shadow: 0 20px 50px rgba(15, 23, 42, 0.08);
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.feature-strip h2 {
  margin: 0;
  font-size: 1.25rem;
}

.feature-strip p {
  margin: 0;
  color: rgba(15, 23, 42, 0.7);
}

.cta-panel {
  display: flex;
  justify-content: center;
}

.cta-card {
  max-width: 720px;
  width: 100%;
  background: linear-gradient(135deg, rgba(79, 70, 229, 0.95), rgba(14, 165, 233, 0.9));
  color: #fff;
  padding: 3rem;
  border-radius: 32px;
  box-shadow: 0 30px 60px rgba(14, 165, 233, 0.25);
  display: flex;
  flex-direction: column;
  gap: 1rem;
  text-align: center;
}

.cta-card h2 {
  margin: 0;
  font-size: clamp(2rem, 2vw + 1rem, 2.75rem);
}

.cta-card p {
  margin: 0;
  color: rgba(255, 255, 255, 0.85);
}

.site-footer {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 1rem;
  padding: 2.5rem 6vw;
  background: rgba(15, 23, 42, 0.92);
  color: rgba(226, 232, 240, 0.95);
}

.site-footer p {
  margin: 0;
  color: rgba(226, 232, 240, 0.75);
}

.site-footer a {
  color: inherit;
  text-decoration: underline;
}

@media (max-width: 1024px) {
  .nav-links {
    display: none;
  }

  .hero {
    grid-template-columns: 1fr;
    text-align: center;
  }

  .hero-copy {
    align-items: center;
  }

  .hero-subtitle {
    max-width: 100%;
  }

  .hero-media {
    order: -1;
  }
}

@media (max-width: 600px) {
  .top-nav {
    padding: 1rem 5vw;
  }

  main {
    padding: 2.5rem 5vw 3rem;
    gap: 4rem;
  }

  .cta-card {
    padding: 2.5rem 2rem;
  }
}
</style>

