<script setup>
const reasons = [
  {
    title: 'Ship Code From Day One',
    description: 'I\'ve worked across the full stack in production environments. I understand deployment pipelines, database migrations, and production debugging. Contribute value from day one, not month one.'
  },
  {
    title: 'Write Maintainable Code',
    description: 'Clear naming, sensible abstractions, documented edge cases. I\'ve inherited enough legacy code to know what makes future developers struggle—and I actively prevent it through clean architecture.'
  },
  {
    title: 'Own Features End-to-End',
    description: 'From database schema to API design to frontend implementation. I don\'t throw code over the wall—I ship complete features, monitor them in production, and iterate based on real user data.'
  },
  {
    title: 'Prevent Issues Before They Happen',
    description: 'I\'ve debugged production outages at 2 AM, fixed database locks during peak traffic, and hunted memory leaks. This experience means I build systems that don\'t break under pressure.'
  }
]
</script>

<template>
  <section class="why-hire">
    <div class="container">
      <h2 class="section-title">Why Hire Me</h2>

      <div class="reasons-grid">
        <div
          v-for="(reason, index) in reasons"
          :key="index"
          class="reason-card"
        >
          <div class="reason-number">{{ String(index + 1).padStart(2, '0') }}</div>
          <h3 class="reason-title">{{ reason.title }}</h3>
          <p class="reason-description">{{ reason.description }}</p>
        </div>
      </div>

      <div class="hire-summary">
        <p>
          <strong>You're not hiring a junior who needs hand-holding.</strong> You're getting a proven full-stack engineer with 3 years of production experience, ready to contribute from day one. I take ownership, ship quality code, and deliver measurable business impact.
        </p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.why-hire {
  position: relative;
  padding: 6rem 2rem;
  background: linear-gradient(180deg, #121218 0%, #0f0f0f 50%, #0a0a0f 100%);
  overflow: hidden;
}

.why-hire::before {
  content: '';
  position: absolute;
  top: -100px;
  left: -100px;
  width: 400px;
  height: 400px;
  background: radial-gradient(circle, rgba(74, 144, 226, 0.12) 0%, transparent 70%);
  filter: blur(70px);
  pointer-events: none;
}

.why-hire::after {
  content: '';
  position: absolute;
  bottom: -100px;
  right: -100px;
  width: 450px;
  height: 450px;
  background: radial-gradient(circle, rgba(155, 89, 182, 0.1) 0%, transparent 70%);
  filter: blur(70px);
  pointer-events: none;
}

.container {
  position: relative;
  max-width: 1400px;
  margin: 0 auto;
  z-index: 1;
}

.section-title {
  font-size: 2.5rem;
  font-weight: 700;
  text-align: center;
  margin: 0 0 4rem;
  background: linear-gradient(135deg, #ffffff 0%, #64ffda 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.reasons-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1.5rem;
  margin-bottom: 3.5rem;
}

.reason-card {
  position: relative;
  background: linear-gradient(135deg, rgba(26, 26, 46, 0.5) 0%, rgba(20, 20, 35, 0.5) 100%);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(100, 255, 218, 0.1);
  border-radius: 16px;
  padding: 2rem;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  overflow: hidden;
}

.reason-card::before {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, rgba(100, 255, 218, 0.05) 0%, transparent 100%);
  opacity: 0;
  transition: opacity 0.4s ease;
  pointer-events: none;
}

.reason-card:hover {
  border-color: rgba(100, 255, 218, 0.4);
  transform: translateY(-6px);
  box-shadow:
    0 16px 32px rgba(0, 0, 0, 0.3),
    0 0 20px rgba(100, 255, 218, 0.1);
}

.reason-card:hover::before {
  opacity: 1;
}

.reason-number {
  position: relative;
  z-index: 1;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  font-size: 1rem;
  font-weight: 700;
  color: #0f0f0f;
  background: linear-gradient(135deg, #64ffda 0%, #4a90e2 100%);
  border-radius: 10px;
  margin-bottom: 1.25rem;
  transition: transform 0.3s ease;
}

.reason-card:hover .reason-number {
  transform: scale(1.1) rotate(5deg);
}

.reason-title {
  position: relative;
  z-index: 1;
  font-size: 1.25rem;
  font-weight: 700;
  color: #ffffff;
  margin: 0 0 1rem;
  transition: color 0.3s ease;
}

.reason-card:hover .reason-title {
  color: #64ffda;
}

.reason-description {
  position: relative;
  z-index: 1;
  font-size: 0.9375rem;
  color: #b0b0b0;
  line-height: 1.7;
  margin: 0;
  transition: color 0.3s ease;
}

.reason-card:hover .reason-description {
  color: #d0d0d0;
}

.hire-summary {
  position: relative;
  background: linear-gradient(135deg, rgba(100, 255, 218, 0.15) 0%, rgba(74, 144, 226, 0.1) 100%);
  backdrop-filter: blur(10px);
  border: 2px solid rgba(100, 255, 218, 0.3);
  border-radius: 20px;
  padding: 2.5rem;
  text-align: center;
  overflow: hidden;
  transition: all 0.4s ease;
}

.hire-summary::before {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(circle at center, rgba(100, 255, 218, 0.1) 0%, transparent 70%);
  opacity: 0;
  transition: opacity 0.4s ease;
  pointer-events: none;
}

.hire-summary:hover {
  border-color: rgba(100, 255, 218, 0.5);
  box-shadow:
    0 12px 24px rgba(0, 0, 0, 0.3),
    0 0 30px rgba(100, 255, 218, 0.2);
  transform: scale(1.02);
}

.hire-summary:hover::before {
  opacity: 1;
}

.hire-summary p {
  position: relative;
  z-index: 1;
  font-size: 1.25rem;
  color: #e0e0e0;
  line-height: 1.8;
  margin: 0;
  font-weight: 600;
}

@media (max-width: 1200px) {
  .reasons-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 768px) {
  .section-title {
    font-size: 2rem;
  }

  .reasons-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }

  .hire-summary {
    padding: 2rem;
  }

  .hire-summary p {
    font-size: 1.125rem;
  }
}
</style>
