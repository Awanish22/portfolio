<script setup>
const highlights = [
  {
    icon: '🚀',
    metric: '10K+',
    label: 'Active Users Served',
    description: 'Built and scaled the Biltrax platform from zero to production'
  },
  {
    icon: '⚡',
    metric: '<2s',
    label: 'Dashboard Load Time',
    description: 'Optimized data-heavy dashboards through query optimization and caching'
  },
  {
    icon: '🎯',
    metric: '40%',
    label: 'Performance Improvement',
    description: 'Reduced page load times through Vue.js migration and optimization'
  },
  {
    icon: '✅',
    metric: 'Zero',
    label: 'Downtime Migrations',
    description: 'Executed major frontend and backend migrations without production incidents'
  }
]
</script>

<template>
  <section id="highlights" class="highlights">
    <div class="container">
      <h2 class="section-title">Impact at a Glance</h2>
      <p class="section-subtitle">Numbers that matter to your business</p>

      <div class="highlights-grid">
        <div
          v-for="(highlight, index) in highlights"
          :key="index"
          class="highlight-card"
        >
          <div class="highlight-icon">{{ highlight.icon }}</div>
          <div class="highlight-metric">{{ highlight.metric }}</div>
          <div class="highlight-label">{{ highlight.label }}</div>
          <p class="highlight-description">{{ highlight.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.highlights {
  position: relative;
  padding: 6rem 2rem;
  background: linear-gradient(180deg, #1a1a2e 0%, #0f0f1a 50%, #121218 100%);
  overflow: hidden;
}

.highlights::before {
  content: '';
  position: absolute;
  top: -200px;
  left: 50%;
  transform: translateX(-50%);
  width: 600px;
  height: 600px;
  background: radial-gradient(circle, rgba(100, 255, 218, 0.08) 0%, transparent 70%);
  filter: blur(80px);
  pointer-events: none;
}

.container {
  position: relative;
  max-width: 1200px;
  margin: 0 auto;
  z-index: 1;
}

.section-title {
  font-size: 2.5rem;
  font-weight: 700;
  text-align: center;
  margin: 0 0 0.5rem;
  background: linear-gradient(135deg, #ffffff 0%, #64ffda 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.section-subtitle {
  font-size: 1.125rem;
  color: #808080;
  text-align: center;
  margin: 0 0 4rem;
}

.highlights-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 2rem;
}

.highlight-card {
  position: relative;
  background: linear-gradient(135deg, rgba(26, 26, 46, 0.6) 0%, rgba(20, 20, 35, 0.6) 100%);
  backdrop-filter: blur(15px);
  border: 1px solid rgba(100, 255, 218, 0.15);
  border-radius: 20px;
  padding: 2.5rem 2rem;
  text-align: center;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  overflow: hidden;
}

.highlight-card::before {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(circle at center, rgba(100, 255, 218, 0.05) 0%, transparent 70%);
  opacity: 0;
  transition: opacity 0.4s ease;
  pointer-events: none;
}

.highlight-card::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 3px;
  background: linear-gradient(90deg, #64ffda 0%, #4a90e2 100%);
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

.highlight-card:hover {
  border-color: rgba(100, 255, 218, 0.4);
  transform: translateY(-8px);
  box-shadow:
    0 20px 40px rgba(0, 0, 0, 0.3),
    0 0 30px rgba(100, 255, 218, 0.15);
}

.highlight-card:hover::before {
  opacity: 1;
}

.highlight-card:hover::after {
  transform: scaleX(1);
}

.highlight-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
  animation: float 3s ease-in-out infinite;
}

@keyframes float {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
}

.highlight-metric {
  position: relative;
  z-index: 1;
  font-size: 3rem;
  font-weight: 800;
  background: linear-gradient(135deg, #64ffda 0%, #4a90e2 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  margin-bottom: 0.5rem;
  line-height: 1.2;
  transition: transform 0.3s ease;
}

.highlight-card:hover .highlight-metric {
  transform: scale(1.1);
}

.highlight-label {
  position: relative;
  z-index: 1;
  font-size: 1rem;
  font-weight: 700;
  color: #ffffff;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  margin-bottom: 1rem;
  transition: color 0.3s ease;
}

.highlight-card:hover .highlight-label {
  color: #64ffda;
}

.highlight-description {
  position: relative;
  z-index: 1;
  font-size: 0.9375rem;
  color: #b0b0b0;
  line-height: 1.7;
  margin: 0;
  transition: color 0.3s ease;
}

.highlight-card:hover .highlight-description {
  color: #d0d0d0;
}

@media (max-width: 768px) {
  .section-title {
    font-size: 2rem;
  }

  .highlights-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }

  .highlight-metric {
    font-size: 2.5rem;
  }
}
</style>
