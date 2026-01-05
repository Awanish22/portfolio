<script setup>
const caseStudies = [
  {
    id: 1,
    title: 'Biltrax Platform: Construction Intelligence at Scale',
    problem: 'Building a construction intelligence platform from scratch to handle massive datasets of projects, leads, and user data. Needed to support consultants, contractors, and building material manufacturers with complex BI workflows. Initial architecture struggled with query performance and dashboard rendering times.',
    decisions: [
      'Built RESTful APIs with Laravel, implementing role-based access control and multi-tenant data isolation for secure data handling.',
      'Designed optimized MySQL database schemas with proper indexing and relationships to handle complex construction project data.',
      'Created responsive Vue.js dashboards with data-intensive views, implementing virtual scrolling for large datasets.',
      'Optimized database queries and API response times through query profiling, eager loading, and Redis caching.',
      'Implemented background job processing for heavy operations like data imports and report generation.',
      'Integrated third-party APIs for construction data aggregation and enrichment.'
    ],
    impact: '✅ Scaled platform to 10K+ active users with <2s dashboard load times\n✅ Zero downtime during production migrations\n✅ Delivered lead generation features that became core revenue drivers\n✅ Saved 40+ hours/month in manual reporting for business teams\n✅ Reduced support tickets by 35% through better error handling'
  },
  {
    id: 2,
    title: 'Legacy Migration: Zero-Downtime Vue.js Refactor',
    problem: 'Legacy frontend components built with outdated Vue.js patterns were becoming unmaintainable. Code duplication, poor state management, and performance issues affecting user experience. Business required continuous availability during migration.',
    decisions: [
      'Planned incremental migration strategy—refactored components in isolated modules to minimize risk.',
      'Introduced Vuex/Pinia for centralized state management, eliminating prop-drilling and component coupling.',
      'Implemented component composition patterns and reusable abstractions for common UI patterns.',
      'Conducted thorough testing of each migrated module before deployment.',
      'Used feature flags to gradually roll out new components to users.',
      'Optimized bundle sizes and implemented code-splitting for faster initial loads.'
    ],
    impact: '✅ Zero production incidents during entire migration\n✅ Improved page load times by 40%\n✅ Doubled developer velocity—features ship 2x faster\n✅ Reduced bug reports by 60% through better architecture\n✅ Enabled team to onboard new developers 50% faster'
  },
  {
    id: 3,
    title: 'E-Commerce Platform: End-to-End Shopping Experience',
    problem: 'Client needed a full-featured e-commerce solution to sell products online. Required seamless shopping experience with inventory management, secure payments, and comprehensive admin controls. Previous solution had high cart abandonment rates and manual inventory tracking.',
    decisions: [
      'Built product catalog with advanced filtering, sorting, and category-based navigation using Laravel and Vue.js.',
      'Implemented shopping cart with persistent sessions and real-time price calculations.',
      'Integrated Stripe/Razorpay payment gateways with secure checkout flow and order confirmation.',
      'Developed inventory management system with real-time stock tracking and low-stock alerts.',
      'Created order management workflow with status tracking, invoicing, and shipping integration.',
      'Built admin dashboard for sales analytics, customer insights, and revenue reporting.'
    ],
    impact: '✅ Reduced cart abandonment by 35% through optimized checkout flow\n✅ Automated inventory tracking saved 20+ hours/week in manual work\n✅ Real-time stock alerts prevented overselling incidents\n✅ Sales dashboard enabled data-driven business decisions\n✅ Secure payment integration increased customer trust'
  },
  {
    id: 4,
    title: 'Educational Platform: Learning Management System',
    problem: 'Educational institution needed an online learning platform to deliver courses remotely. Required course management, student enrollment, progress tracking, and certification features. Existing process was manual and couldn\'t scale with growing student base.',
    decisions: [
      'Developed course creation module with video uploads, quizzes, assignments, and progress tracking.',
      'Implemented student dashboard with enrolled courses, completion certificates, and performance analytics.',
      'Built instructor panel for content management, student progress monitoring, and grading.',
      'Integrated video streaming with adaptive quality for seamless playback across devices.',
      'Created subscription-based access with payment gateway integration for course purchases.',
      'Implemented gamification elements like badges and leaderboards to boost engagement.'
    ],
    impact: '✅ Enabled 5000+ students to learn remotely with seamless experience\n✅ Reduced administrative overhead by 60% through automation\n✅ Course completion rates increased by 45% with progress tracking\n✅ Automated certificate generation saved 30+ hours/month\n✅ Scalable architecture handled 10x traffic during peak enrollment'
  },
  {
    id: 5,
    title: 'Job Portal: Connecting Talent with Opportunities',
    problem: 'Recruitment agency needed a platform to connect job seekers with employers efficiently. Manual processes for job posting, application tracking, and candidate matching were time-consuming. Required advanced search capabilities and streamlined hiring workflow.',
    decisions: [
      'Built job posting and management system with applicant tracking for employers.',
      'Developed candidate profiles with resume upload, skills matching, and job recommendations.',
      'Implemented advanced job search with Elasticsearch for location, salary, experience, and skill-based filters.',
      'Created application workflow with status updates, interview scheduling, and communication tools.',
      'Built admin dashboard for platform analytics, user management, and content moderation.',
      'Implemented email notifications for job alerts, application updates, and interview reminders.'
    ],
    impact: '✅ Reduced time-to-hire by 40% through streamlined application process\n✅ Smart matching algorithm improved candidate-job fit by 50%\n✅ Automated notifications reduced missed interviews by 70%\n✅ Advanced search helped candidates find relevant jobs 3x faster\n✅ Platform scaled to handle 10K+ active job listings'
  }
]
</script>

<template>
  <section id="case-studies" class="case-studies">
    <div class="container">
      <h2 class="section-title">Case Studies</h2>
      <p class="section-subtitle">Problem → Decision → Impact</p>

      <div class="studies-grid">
        <article
          v-for="study in caseStudies"
          :key="study.id"
          class="study-card"
        >
          <h3 class="study-title">{{ study.title }}</h3>

          <div class="study-section">
            <h4 class="study-label">The Problem</h4>
            <p class="study-content">{{ study.problem }}</p>
          </div>

          <div class="study-section">
            <h4 class="study-label">Key Decisions</h4>
            <ul class="decisions-list">
              <li
                v-for="(decision, index) in study.decisions"
                :key="index"
                class="decision-item"
              >
                {{ decision }}
              </li>
            </ul>
          </div>

          <div class="study-section study-impact">
            <h4 class="study-label">Impact</h4>
            <p class="study-content impact-text">{{ study.impact }}</p>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>

<style scoped>
.case-studies {
  position: relative;
  padding: 6rem 2rem;
  background: linear-gradient(180deg, #0a0a0f 0%, #0f0f0f 50%, #121218 100%);
  overflow: hidden;
}

.case-studies::before {
  content: '';
  position: absolute;
  bottom: 0;
  right: 0;
  width: 500px;
  height: 500px;
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

.studies-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(500px, 1fr));
  gap: 2.5rem;
}

@media (max-width: 600px) {
  .studies-grid {
    grid-template-columns: 1fr;
  }
}

.study-card {
  position: relative;
  background: linear-gradient(135deg, rgba(26, 26, 46, 0.6) 0%, rgba(20, 20, 35, 0.6) 100%);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(100, 255, 218, 0.15);
  border-radius: 20px;
  padding: 2.5rem;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  overflow: hidden;
}

.study-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(90deg, #64ffda 0%, #4a90e2 50%, #9b59b6 100%);
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.5s cubic-bezier(0.4, 0, 0.2, 1);
}

.study-card::after {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(circle at top right, rgba(100, 255, 218, 0.05) 0%, transparent 70%);
  opacity: 0;
  transition: opacity 0.4s ease;
  pointer-events: none;
}

.study-card:hover {
  border-color: rgba(100, 255, 218, 0.4);
  transform: translateY(-8px);
  box-shadow:
    0 24px 48px rgba(0, 0, 0, 0.4),
    0 0 40px rgba(100, 255, 218, 0.15);
}

.study-card:hover::before {
  transform: scaleX(1);
}

.study-card:hover::after {
  opacity: 1;
}

.study-title {
  position: relative;
  z-index: 1;
  font-size: 1.5rem;
  font-weight: 700;
  color: #ffffff;
  margin: 0 0 1.75rem;
  padding-bottom: 1.25rem;
  border-bottom: 2px solid rgba(100, 255, 218, 0.2);
  transition: color 0.3s ease;
}

.study-card:hover .study-title {
  color: #64ffda;
}

.study-section {
  position: relative;
  z-index: 1;
  margin-bottom: 1.75rem;
}

.study-section:last-child {
  margin-bottom: 0;
}

.study-label {
  font-size: 0.75rem;
  font-weight: 700;
  color: #4a90e2;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  margin: 0 0 0.875rem;
  display: inline-block;
  padding: 0.25rem 0.75rem;
  background: rgba(74, 144, 226, 0.1);
  border-radius: 4px;
}

.study-content {
  font-size: 1rem;
  color: #b0b0b0;
  line-height: 1.8;
  margin: 0;
  transition: color 0.3s ease;
}

.study-card:hover .study-content {
  color: #d0d0d0;
}

.decisions-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 0.875rem;
}

.decision-item {
  position: relative;
  padding-left: 1.5rem;
  font-size: 0.9375rem;
  color: #b0b0b0;
  line-height: 1.7;
  transition: all 0.3s ease;
}

.decision-item::before {
  content: '▹';
  position: absolute;
  left: 0;
  color: #64ffda;
  font-size: 1.125rem;
  transition: transform 0.3s ease;
}

.decision-item:hover {
  color: #e0e0e0;
  padding-left: 2rem;
}

.decision-item:hover::before {
  transform: translateX(0.25rem);
}

.study-impact {
  position: relative;
  background: linear-gradient(135deg, rgba(100, 255, 218, 0.1) 0%, rgba(74, 144, 226, 0.1) 100%);
  backdrop-filter: blur(5px);
  border: 1px solid rgba(100, 255, 218, 0.2);
  margin: 2rem -2.5rem -2.5rem;
  padding: 2rem 2.5rem;
  border-radius: 0 0 20px 20px;
}

.impact-text {
  color: #e0e0e0;
  font-weight: 500;
  font-size: 1.0625rem;
  line-height: 1.9;
  white-space: pre-line;
}

@media (max-width: 768px) {
  .section-title {
    font-size: 2rem;
  }

  .studies-grid {
    grid-template-columns: 1fr;
  }

  .study-card {
    padding: 2rem;
  }

  .study-impact {
    margin: 1.5rem -2rem -2rem;
    padding: 1.5rem 2rem;
  }
}
</style>
