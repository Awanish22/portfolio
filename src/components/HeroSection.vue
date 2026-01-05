<script setup>
import { onMounted, ref } from 'vue'

defineProps({
  name: {
    type: String,
    default: 'Your Name'
  }
})

const isVisible = ref(false)

onMounted(() => {
  setTimeout(() => {
    isVisible.value = true
  }, 100)
})

const downloadResume = () => {
  window.open('/resume.html', '_blank')
}

</script>

<template>
  <section class="hero">
    <div class="hero-bg">
      <div class="gradient-orb orb-1"></div>
      <div class="gradient-orb orb-2"></div>
      <div class="gradient-orb orb-3"></div>
    </div>

    <div class="hero-content" :class="{ 'fade-in': isVisible }">
      <div class="badge">
        <span class="badge-dot"></span>
        Available for hire
      </div>

      <h1 class="hero-title">
        <span class="gradient-text">{{ name }}</span>
      </h1>

      <p class="hero-subtitle">
        <span class="typing-effect">Senior Full-Stack Engineer</span>
      </p>

      <p class="hero-tagline">
        I build production-grade systems that scale. 3 years shipping features for 10K+ users—from Laravel APIs to Vue.js dashboards that load in under 2 seconds.
      </p>

      <div class="hero-stats">
        <div class="stat-item">
          <div class="stat-value">3+</div>
          <div class="stat-label">Years Experience</div>
        </div>
        <div class="stat-divider"></div>
        <div class="stat-item">
          <div class="stat-value">10+</div>
          <div class="stat-label">Projects Delivered</div>
        </div>
        <div class="stat-divider"></div>
        <div class="stat-item">
          <div class="stat-value">Full-Stack</div>
          <div class="stat-label">Development</div>
        </div>
      </div>

      <p class="hero-context">
        <strong>Tech Stack:</strong> Laravel · Vue.js · Node.js · MySQL · Redis · REST APIs
      </p>

      <div class="hero-cta">
        <a href="#contact" class="btn btn-primary">
          <span>Let's Talk</span>
          <svg width="16" height="16" viewBox="0 0 16 16" fill="none">
            <path d="M8 1L15 8L8 15M15 8H1" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </a>
        <button @click="downloadResume" class="btn btn-resume">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="none">
            <path d="M8 1V10M8 10L4 6M8 10L12 6" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M1 13H15" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
          </svg>
          <span>Download Resume</span>
        </button>
        <a href="#case-studies" class="btn btn-secondary">
          <span>See My Work</span>
        </a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 4rem 2rem;
  background: linear-gradient(135deg, #0a0a0f 0%, #1a1a2e 50%, #16213e 100%);
  overflow: hidden;
}

.hero-bg {
  position: absolute;
  inset: 0;
  overflow: hidden;
  z-index: 0;
}

.gradient-orb {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
  opacity: 0.4;
  animation: float 20s infinite ease-in-out;
}

.orb-1 {
  width: 500px;
  height: 500px;
  background: radial-gradient(circle, #64ffda 0%, transparent 70%);
  top: -200px;
  left: -200px;
  animation-delay: 0s;
}

.orb-2 {
  width: 400px;
  height: 400px;
  background: radial-gradient(circle, #4a90e2 0%, transparent 70%);
  bottom: -150px;
  right: -150px;
  animation-delay: -7s;
}

.orb-3 {
  width: 350px;
  height: 350px;
  background: radial-gradient(circle, #9b59b6 0%, transparent 70%);
  top: 50%;
  right: 10%;
  animation-delay: -14s;
}

@keyframes float {
  0%, 100% {
    transform: translate(0, 0) scale(1);
  }
  33% {
    transform: translate(30px, -50px) scale(1.1);
  }
  66% {
    transform: translate(-20px, 20px) scale(0.9);
  }
}

.hero-content {
  position: relative;
  z-index: 1;
  max-width: 800px;
  text-align: center;
  opacity: 0;
  transform: translateY(30px);
  transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1);
}

.hero-content.fade-in {
  opacity: 1;
  transform: translateY(0);
}

.badge {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  background: rgba(100, 255, 218, 0.1);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(100, 255, 218, 0.3);
  border-radius: 50px;
  padding: 0.5rem 1.25rem;
  margin-bottom: 2rem;
  font-size: 0.875rem;
  color: #64ffda;
  font-weight: 500;
  animation: slideDown 0.8s ease-out 0.2s both;
}

.badge-dot {
  width: 8px;
  height: 8px;
  background: #64ffda;
  border-radius: 50%;
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0%, 100% {
    opacity: 1;
    box-shadow: 0 0 0 0 rgba(100, 255, 218, 0.7);
  }
  50% {
    opacity: 0.8;
    box-shadow: 0 0 0 8px rgba(100, 255, 218, 0);
  }
}

@keyframes slideDown {
  from {
    opacity: 0;
    transform: translateY(-20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.hero-title {
  font-size: clamp(2.5rem, 6vw, 4.5rem);
  font-weight: 700;
  margin: 0 0 1rem;
  letter-spacing: -0.02em;
  animation: fadeInUp 0.8s ease-out 0.4s both;
}

.gradient-text {
  background: linear-gradient(135deg, #ffffff 0%, #64ffda 50%, #4a90e2 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  animation: shimmer 8s linear infinite;
  background-size: 200% 200%;
}

@keyframes shimmer {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

.hero-subtitle {
  font-size: 1.75rem;
  color: #64ffda;
  margin: 0 0 2rem;
  font-weight: 500;
  animation: fadeInUp 0.8s ease-out 0.6s both;
}

.typing-effect {
  display: inline-block;
  position: relative;
}

.typing-effect::after {
  content: '|';
  animation: blink 1s step-end infinite;
  margin-left: 2px;
}

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}

.hero-tagline {
  font-size: 1.25rem;
  color: #e0e0e0;
  line-height: 1.6;
  margin: 0 0 2.5rem;
  max-width: 650px;
  margin-left: auto;
  margin-right: auto;
  animation: fadeInUp 0.8s ease-out 0.8s both;
}

.hero-stats {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1rem;
  margin: 3rem 0;
  animation: fadeInUp 0.8s ease-out 1s both;
}

.stat-item {
  position: relative;
  text-align: center;
  padding: 1.75rem 2.25rem;
  background: linear-gradient(135deg, rgba(26, 26, 46, 0.6) 0%, rgba(20, 20, 35, 0.6) 100%);
  backdrop-filter: blur(15px);
  border: 1px solid rgba(100, 255, 218, 0.15);
  border-radius: 16px;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  overflow: hidden;
  min-width: 140px;
}

.stat-item::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 3px;
  background: linear-gradient(90deg, #64ffda 0%, #4a90e2 100%);
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

.stat-item:hover {
  border-color: rgba(100, 255, 218, 0.4);
  transform: translateY(-6px);
  box-shadow:
    0 12px 24px rgba(0, 0, 0, 0.3),
    0 0 20px rgba(100, 255, 218, 0.15);
}

.stat-item:hover::before {
  transform: scaleX(1);
}

.stat-value {
  position: relative;
  z-index: 1;
  font-size: 2.25rem;
  font-weight: 800;
  background: linear-gradient(135deg, #64ffda 0%, #4a90e2 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  line-height: 1.2;
  margin-bottom: 0.625rem;
  transition: transform 0.3s ease;
}

.stat-item:hover .stat-value {
  transform: scale(1.08);
}

.stat-label {
  position: relative;
  z-index: 1;
  font-size: 0.8125rem;
  color: #a0a0a0;
  text-transform: uppercase;
  letter-spacing: 0.12em;
  font-weight: 600;
  transition: color 0.3s ease;
}

.stat-item:hover .stat-label {
  color: #64ffda;
}

.stat-divider {
  width: 2px;
  height: 60px;
  background: linear-gradient(to bottom, transparent 0%, #64ffda 50%, transparent 100%);
  opacity: 0.3;
}

.hero-context {
  font-size: 1rem;
  color: #a0a0a0;
  line-height: 1.8;
  margin: 0 0 2.5rem;
  animation: fadeInUp 0.8s ease-out 1.2s both;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.hero-cta {
  display: flex;
  gap: 1rem;
  justify-content: center;
  flex-wrap: wrap;
  animation: fadeInUp 0.8s ease-out 1.4s both;
}

.btn {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 1rem 2.25rem;
  font-size: 1rem;
  font-weight: 600;
  border-radius: 8px;
  text-decoration: none;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  cursor: pointer;
  position: relative;
  overflow: hidden;
}

.btn::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  width: 0;
  height: 0;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.2);
  transform: translate(-50%, -50%);
  transition: width 0.6s, height 0.6s;
}

.btn:hover::before {
  width: 300px;
  height: 300px;
}

.btn span {
  position: relative;
  z-index: 1;
}

.btn svg {
  position: relative;
  z-index: 1;
  transition: transform 0.3s ease;
}

.btn:hover svg {
  transform: translateX(4px);
}

.btn-primary {
  background: linear-gradient(135deg, #64ffda 0%, #4fd1b0 100%);
  color: #0f0f0f;
  box-shadow: 0 4px 15px rgba(100, 255, 218, 0.3);
}

.btn-primary:hover {
  box-shadow: 0 6px 25px rgba(100, 255, 218, 0.5);
  transform: translateY(-3px);
}

.btn-primary:active {
  transform: translateY(-1px);
}

.btn-secondary {
  background: rgba(100, 255, 218, 0.05);
  color: #64ffda;
  border: 2px solid #64ffda;
  backdrop-filter: blur(10px);
}

.btn-secondary:hover {
  background: rgba(100, 255, 218, 0.15);
  border-color: #4fd1b0;
  transform: translateY(-3px);
  box-shadow: 0 4px 20px rgba(100, 255, 218, 0.2);
}

.btn-secondary:active {
  transform: translateY(-1px);
}

.btn-resume {
  background: linear-gradient(135deg, #4a90e2 0%, #5a67d8 100%);
  color: #ffffff;
  border: none;
  box-shadow: 0 4px 15px rgba(74, 144, 226, 0.3);
}

.btn-resume:hover {
  box-shadow: 0 6px 25px rgba(74, 144, 226, 0.5);
  transform: translateY(-3px);
}

.btn-resume:hover svg {
  transform: translateY(2px);
}

.btn-resume:active {
  transform: translateY(-1px);
}

@media (max-width: 768px) {
  .hero-stats {
    flex-wrap: wrap;
    gap: 1rem;
  }

  .stat-item {
    padding: 1.5rem 1.75rem;
    min-width: 120px;
  }

  .stat-value {
    font-size: 1.875rem;
  }

  .stat-label {
    font-size: 0.75rem;
  }

  .stat-divider {
    display: none;
  }
}

@media (max-width: 480px) {
  .hero-stats {
    gap: 0.75rem;
  }

  .stat-item {
    padding: 1.25rem 1.5rem;
    min-width: 100px;
  }

  .stat-value {
    font-size: 1.625rem;
  }
}
</style>
