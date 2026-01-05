<script setup>
const propositions = [
  {
    title: 'I Ship Production Code',
    description: 'Not prototypes. Not tutorials. Real systems handling real users, real data, real edge cases. Every line I write goes to production and stays there.'
  },
  {
    title: 'I Own Problems End-to-End',
    description: 'From database schema to API design to frontend state management. I don\'t throw code over the wall. I ship features that work and maintain them.'
  },
  {
    title: 'I Build for Scale Before It\'s Needed',
    description: 'Query optimization, caching strategies, background jobs, queue management. I\'ve learned the hard way what breaks at 10x traffic—so I prevent it upfront.'
  }
]
</script>

<template>
  <section class="value-proposition">
    <div class="container">
      <h2 class="section-title">What You Get</h2>
      <div class="propositions-grid">
        <div
          v-for="(prop, index) in propositions"
          :key="index"
          class="proposition-card"
        >
          <h3 class="proposition-title">{{ prop.title }}</h3>
          <p class="proposition-description">{{ prop.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.value-proposition {
  position: relative;
  padding: 6rem 2rem;
  background: linear-gradient(180deg, #0f0f0f 0%, #0a0a0f 100%);
}

.container {
  max-width: 1100px;
  margin: 0 auto;
}

.section-title {
  font-size: 2.5rem;
  font-weight: 700;
  color: #ffffff;
  text-align: center;
  margin: 0 0 1rem;
  background: linear-gradient(135deg, #ffffff 0%, #64ffda 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.propositions-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2rem;
  margin-top: 4rem;
}

.proposition-card {
  position: relative;
  background: linear-gradient(135deg, rgba(26, 26, 46, 0.8) 0%, rgba(20, 20, 35, 0.8) 100%);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(100, 255, 218, 0.1);
  border-radius: 16px;
  padding: 2.5rem;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  overflow: hidden;
}

.proposition-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 3px;
  background: linear-gradient(90deg, #64ffda 0%, #4a90e2 50%, #9b59b6 100%);
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

.proposition-card::after {
  content: '';
  position: absolute;
  top: -50%;
  right: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(circle, rgba(100, 255, 218, 0.1) 0%, transparent 70%);
  opacity: 0;
  transition: opacity 0.4s ease;
  pointer-events: none;
}

.proposition-card:hover {
  border-color: rgba(100, 255, 218, 0.4);
  transform: translateY(-8px);
  box-shadow:
    0 20px 40px rgba(0, 0, 0, 0.4),
    0 0 30px rgba(100, 255, 218, 0.1);
}

.proposition-card:hover::before {
  transform: scaleX(1);
}

.proposition-card:hover::after {
  opacity: 1;
}

.proposition-title {
  font-size: 1.375rem;
  font-weight: 600;
  color: #ffffff;
  margin: 0 0 1.25rem;
  position: relative;
  z-index: 1;
  transition: color 0.3s ease;
}

.proposition-card:hover .proposition-title {
  color: #64ffda;
}

.proposition-description {
  font-size: 1rem;
  color: #b0b0b0;
  line-height: 1.8;
  margin: 0;
  position: relative;
  z-index: 1;
  transition: color 0.3s ease;
}

.proposition-card:hover .proposition-description {
  color: #d0d0d0;
}

@media (max-width: 768px) {
  .propositions-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }

  .section-title {
    font-size: 2rem;
  }
}
</style>
