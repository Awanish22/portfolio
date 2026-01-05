<script setup>
const experiences = [
  {
    role: 'Full-Stack Developer',
    company: 'Noetic IT Services',
    period: 'Dec 2022 - Present · 3 yrs',
    location: 'Mumbai, Maharashtra, India · Remote',
    phases: [
      {
        period: 'Jan 2025 – Present',
        title: 'Scalability, Stability & Advanced Development',
        achievements: [
          'Developing new modules and enhancements focused on scalable BI and analytics features for the Biltrax platform.',
          'Working on backend architecture improvements using Laravel and Node.js to support growth and scalability.',
          'Optimizing frontend performance and user experience for large, data-driven dashboards.',
          'Supporting complex business use cases for consultants, contractors, and building material manufacturers.',
          'Collaborating with team members to maintain code quality, best practices, and long-term maintainability.'
        ]
      },
      {
        period: 'Jan 2024 – Dec 2024',
        title: 'Optimization, Migration & Feature Expansion',
        achievements: [
          'Led performance optimization across backend APIs and frontend pages.',
          'Migrated and refactored legacy frontend components to improved Vue.js architecture for better maintainability.',
          'Optimized database queries, indexing, and API response times, improving overall system performance.',
          'Implemented new business intelligence features for lead generation and project tracking.',
          'Executed frontend and backend migrations while ensuring zero or minimal production downtime.',
          'Strengthened security, validation, and error-handling across APIs.'
        ]
      },
      {
        period: 'Dec 2022 – Dec 2023',
        title: 'Project Foundation & Core Development',
        achievements: [
          'Contributed to building the Biltrax platform from scratch, working across both frontend and backend.',
          'Developed RESTful APIs using Laravel for project data, leads, users, and role-based access control.',
          'Designed and implemented MySQL database schemas, relationships, and core business logic.',
          'Built responsive frontend interfaces using Vue.js, focused on dashboards and data-intensive views.',
          'Integrated third-party APIs and internal services to support construction project intelligence workflows.',
          'Collaborated closely with product and business teams to align technical solutions with market requirements.'
        ]
      }
    ],
    skills: ['Vue.js', 'MySQL', 'API Development', 'Laravel', 'Workbench', 'React.js', 'Node.js']
  },
  {
    role: 'Full-Stack Developer',
    company: 'Millennia Ahead Technologies',
    period: 'Nov 2022 - Jan 2023 · 3 mos',
    location: 'Nagpur, Maharashtra, India · Remote',
    type: 'Part-time',
    achievements: [
      'Worked on MERN stack applications (MongoDB, Express.js, React.js, Node.js).',
      'Developed full-stack features and contributed to project deliverables.'
    ],
    skills: ['MongoDB', 'React.js', 'Express.js', 'Node.js']
  },
  {
    role: 'Web Developer',
    company: 'Brain Quest Consultancy and Training',
    period: 'Jun 2022 - Dec 2022 · 7 mos',
    location: 'Dubai, United Arab Emirates',
    achievements: [
      'Developed web applications using Laravel, Vue.js, and React.js.',
      'Designed and implemented RESTful APIs for various client projects.',
      'Worked with Figma for UI/UX collaboration and implementation.'
    ],
    skills: ['API Development', 'Laravel', 'Figma', 'React.js', 'Vue.js']
  },
  {
    role: 'Full-Stack Developer',
    company: 'NextCache Pvt Ltd',
    period: 'Dec 2021 - May 2022 · 6 mos',
    location: 'Lucknow, Uttar Pradesh, India',
    achievements: [
      'Developed full-stack applications using Laravel framework.',
      'Contributed to various web development projects and maintained codebases.'
    ],
    skills: ['Laravel', 'Full-Stack Development']
  },
  {
    role: 'Full Stack Developer',
    company: '36 Central Training and Development',
    period: 'Aug 2021 - Nov 2021 · 4 mos',
    location: 'Raipur, Chhattisgarh, India',
    type: 'Internship',
    achievements: [
      'Developed RESTful APIs using Laravel and built frontend interfaces with Vue.js.',
      'Gained hands-on experience in full-stack development practices.'
    ],
    skills: ['API Development', 'Laravel', 'Vue.js']
  }
]
</script>

<template>
  <section id="experience" class="experience">
    <div class="container">
      <h2 class="section-title">Experience</h2>
      <p class="section-subtitle">3+ years building production systems. Real impact, real scale.</p>

      <div class="experience-timeline">
        <div
          v-for="(exp, index) in experiences"
          :key="index"
          class="experience-item"
        >
          <div class="experience-header">
            <div class="header-main">
              <h3 class="experience-role">{{ exp.role }}</h3>
              <div class="experience-meta">
                <span class="experience-company">{{ exp.company }}</span>
                <span v-if="exp.type" class="experience-type">· {{ exp.type }}</span>
              </div>
              <div class="experience-details">
                <span class="experience-period">{{ exp.period }}</span>
                <span class="experience-location">{{ exp.location }}</span>
              </div>
            </div>
          </div>

          <!-- For Noetic IT Services with phases -->
          <div v-if="exp.phases" class="phases-container">
            <div
              v-for="(phase, phaseIndex) in exp.phases"
              :key="phaseIndex"
              class="phase-item"
            >
              <div class="phase-header">
                <span class="phase-period">{{ phase.period }}</span>
                <span class="phase-title">{{ phase.title }}</span>
              </div>
              <ul class="achievements-list">
                <li
                  v-for="(achievement, i) in phase.achievements"
                  :key="i"
                  class="achievement-item"
                >
                  {{ achievement }}
                </li>
              </ul>
            </div>
          </div>

          <!-- For other companies without phases -->
          <ul v-else class="achievements-list">
            <li
              v-for="(achievement, i) in exp.achievements"
              :key="i"
              class="achievement-item"
            >
              {{ achievement }}
            </li>
          </ul>

          <!-- Skills tags -->
          <div class="skills-tags">
            <span
              v-for="(skill, i) in exp.skills"
              :key="i"
              class="skill-tag"
            >
              {{ skill }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.experience {
  position: relative;
  padding: 6rem 2rem;
  background: linear-gradient(180deg, #0f0f1a 0%, #121218 50%, #0a0a0f 100%);
  overflow: hidden;
}

.experience::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  width: 600px;
  height: 600px;
  background: radial-gradient(circle, rgba(155, 89, 182, 0.1) 0%, transparent 70%);
  transform: translate(-50%, -50%);
  filter: blur(80px);
  pointer-events: none;
}

.container {
  position: relative;
  max-width: 1000px;
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

.experience-timeline {
  display: flex;
  flex-direction: column;
  gap: 3rem;
  position: relative;
}

.experience-timeline::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  width: 2px;
  background: linear-gradient(180deg, transparent 0%, #64ffda 20%, #64ffda 80%, transparent 100%);
}

.experience-item {
  position: relative;
  padding-left: 3rem;
  background: linear-gradient(135deg, rgba(26, 26, 46, 0.4) 0%, rgba(20, 20, 35, 0.4) 100%);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(100, 255, 218, 0.1);
  border-radius: 16px;
  padding: 2rem 2rem 2rem 3rem;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

.experience-item::before {
  content: '';
  position: absolute;
  left: -6px;
  top: 2rem;
  width: 12px;
  height: 12px;
  background: #64ffda;
  border-radius: 50%;
  box-shadow: 0 0 0 4px rgba(100, 255, 218, 0.2);
  transition: all 0.3s ease;
}

.experience-item:hover {
  border-color: rgba(100, 255, 218, 0.3);
  transform: translateX(8px);
  box-shadow:
    0 16px 32px rgba(0, 0, 0, 0.3),
    0 0 20px rgba(100, 255, 218, 0.1);
}

.experience-item:hover::before {
  box-shadow: 0 0 0 8px rgba(100, 255, 218, 0.3);
  transform: scale(1.2);
}

.experience-header {
  margin-bottom: 1.5rem;
}

.header-main {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.experience-role {
  font-size: 1.5rem;
  font-weight: 700;
  color: #ffffff;
  margin: 0;
  transition: color 0.3s ease;
}

.experience-item:hover .experience-role {
  color: #64ffda;
}

.experience-meta {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 1.125rem;
}

.experience-company {
  color: #64ffda;
  font-weight: 600;
}

.experience-type {
  color: #808080;
  font-size: 0.9375rem;
}

.experience-details {
  display: flex;
  flex-direction: column;
  gap: 0.25rem;
  font-size: 0.9375rem;
  color: #808080;
}

.experience-period {
  font-weight: 500;
}

.experience-location {
  color: #606060;
}

.phases-container {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  margin-bottom: 1.5rem;
}

.phase-item {
  position: relative;
  padding-left: 1.5rem;
  border-left: 2px solid rgba(100, 255, 218, 0.2);
}

.phase-header {
  display: flex;
  flex-direction: column;
  gap: 0.25rem;
  margin-bottom: 1rem;
}

.phase-period {
  font-size: 0.875rem;
  font-weight: 600;
  color: #4a90e2;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.phase-title {
  font-size: 1.125rem;
  font-weight: 600;
  color: #ffffff;
}

.achievements-list {
  list-style: none;
  padding: 0;
  margin: 0 0 1.5rem 0;
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.achievement-item {
  position: relative;
  padding-left: 1.5rem;
  font-size: 0.9375rem;
  color: #b0b0b0;
  line-height: 1.7;
  transition: all 0.3s ease;
}

.achievement-item::before {
  content: '▹';
  position: absolute;
  left: 0;
  color: #64ffda;
  font-size: 1.125rem;
  transition: transform 0.3s ease;
}

.achievement-item:hover {
  color: #e0e0e0;
  padding-left: 2rem;
}

.achievement-item:hover::before {
  transform: translateX(0.25rem);
}

.skills-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.625rem;
}

.skill-tag {
  display: inline-block;
  padding: 0.375rem 0.875rem;
  background: rgba(100, 255, 218, 0.1);
  border: 1px solid rgba(100, 255, 218, 0.2);
  border-radius: 6px;
  font-size: 0.8125rem;
  font-weight: 500;
  color: #64ffda;
  transition: all 0.3s ease;
}

.skill-tag:hover {
  background: rgba(100, 255, 218, 0.2);
  border-color: rgba(100, 255, 218, 0.4);
  transform: translateY(-2px);
}

@media (max-width: 768px) {
  .experience-timeline::before {
    left: -1rem;
  }

  .experience-item {
    padding-left: 1.5rem;
  }

  .experience-item::before {
    left: calc(-1rem - 6px);
  }

  .section-title {
    font-size: 2rem;
  }

  .experience-role {
    font-size: 1.25rem;
  }

  .experience-item:hover {
    transform: translateX(4px);
  }
}
</style>
