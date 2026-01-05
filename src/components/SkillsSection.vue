<script setup>
const skillGroups = [
  {
    category: 'Backend & APIs',
    skills: [
      'Laravel',
      'Node.js / Express',
      'REST API Design',
      'Queue Systems',
      'Background Job Processing',
      'Multi-tenancy Architecture'
    ]
  },
  {
    category: 'Databases & Performance',
    skills: [
      'MySQL',
      'Query Optimization',
      'Database Indexing',
      'Materialized Views',
      'ETL Pipelines'
    ]
  },
  {
    category: 'Frontend & Dashboards',
    skills: [
      'Vue.js 2 & 3 (Composition API)',
      'Data Visualization (Charts.js, D3)',
      'Virtual Scrolling / Large Datasets',
      'Responsive SPA Architecture'
    ]
  },
  // {
  //   category: 'DevOps & Infrastructure',
  //   skills: [
  //     'Linux Server Administration',
  //     'Docker / Docker Compose',
  //     'CI/CD (GitHub Actions, GitLab CI)',
  //     'AWS (EC2, RDS, S3, SQS)',
  //     'Nginx Configuration',
  //     'Application Monitoring'
  //   ]
  // }
]
</script>

<template>
  <section id="skills" class="skills">
    <div class="container">
      <h2 class="section-title">Technical Skills</h2>
      <p class="section-subtitle">Grouped by domain. Depth over breadth.</p>

      <div class="skills-grid">
        <div
          v-for="(group, index) in skillGroups"
          :key="index"
          class="skill-group"
        >
          <h3 class="group-title">{{ group.category }}</h3>
          <ul class="skill-list">
            <li
              v-for="(skill, i) in group.skills"
              :key="i"
              class="skill-item"
            >
              {{ skill }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.skills {
  position: relative;
  padding: 6rem 2rem;
  background: linear-gradient(180deg, #0a0a0f 0%, #121218 50%, #0f0f1a 100%);
  overflow: hidden;
}

.skills::before {
  content: '';
  position: absolute;
  top: 0;
  left: 50%;
  width: 500px;
  height: 500px;
  background: radial-gradient(circle, rgba(74, 144, 226, 0.15) 0%, transparent 70%);
  transform: translateX(-50%);
  filter: blur(60px);
  pointer-events: none;
}

.container {
  position: relative;
  max-width: 1100px;
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

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 2rem;
}

.skill-group {
  position: relative;
  background: linear-gradient(135deg, rgba(26, 26, 46, 0.6) 0%, rgba(20, 20, 35, 0.6) 100%);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(100, 255, 218, 0.1);
  border-radius: 16px;
  padding: 2rem;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  overflow: hidden;
}

.skill-group::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, rgba(100, 255, 218, 0.05) 0%, transparent 100%);
  opacity: 0;
  transition: opacity 0.4s ease;
  pointer-events: none;
}

.skill-group:hover {
  border-color: rgba(100, 255, 218, 0.3);
  transform: translateY(-6px);
  box-shadow:
    0 16px 32px rgba(0, 0, 0, 0.3),
    0 0 20px rgba(100, 255, 218, 0.1);
}

.skill-group:hover::before {
  opacity: 1;
}

.group-title {
  font-size: 1.25rem;
  font-weight: 600;
  color: #64ffda;
  margin: 0 0 1.25rem;
  padding-bottom: 0.875rem;
  border-bottom: 2px solid rgba(100, 255, 218, 0.2);
  position: relative;
  transition: color 0.3s ease;
}

.group-title::after {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 0;
  width: 0;
  height: 2px;
  background: linear-gradient(90deg, #64ffda 0%, #4a90e2 100%);
  transition: width 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

.skill-group:hover .group-title::after {
  width: 100%;
}

.skill-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.skill-item {
  position: relative;
  font-size: 0.9375rem;
  color: #b0b0b0;
  padding: 0.75rem 0 0.75rem 1.5rem;
  border-bottom: 1px solid rgba(42, 42, 74, 0.3);
  transition: all 0.3s ease;
}

.skill-item::before {
  content: '▹';
  position: absolute;
  left: 0;
  color: #64ffda;
  font-size: 1.125rem;
  transition: transform 0.3s ease;
}

.skill-item:hover {
  color: #ffffff;
  padding-left: 2rem;
}

.skill-item:hover::before {
  transform: translateX(0.25rem);
}

.skill-item:last-child {
  border-bottom: none;
  padding-bottom: 0;
}

@media (max-width: 768px) {
  .skills-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }

  .section-title {
    font-size: 2rem;
  }
}
</style>
