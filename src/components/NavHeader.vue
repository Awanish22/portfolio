<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})

const downloadResume = () => {
  window.open('/resume.html', '_blank')
}
</script>

<template>
  <header class="nav-header" :class="{ 'scrolled': isScrolled }">
    <div class="nav-container">
      <a href="#" class="nav-logo">
        <span class="logo-text">AK</span>
      </a>

      <nav class="nav-links">
        <a href="#highlights" class="nav-link">Impact</a>
        <a href="#case-studies" class="nav-link">Projects</a>
        <a href="#skills" class="nav-link">Skills</a>
        <a href="#experience" class="nav-link">Experience</a>
        <a href="#contact" class="nav-link">Contact</a>
      </nav>

      <div class="nav-actions">
        <button @click="downloadResume" class="nav-resume-btn">
          <svg width="14" height="14" viewBox="0 0 16 16" fill="none">
            <path d="M8 1V10M8 10L4 6M8 10L12 6" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M1 13H15" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
          </svg>
          <span>Resume</span>
        </button>
        <a href="#contact" class="nav-hire-btn">Hire Me</a>
      </div>

      <button class="mobile-menu-btn" aria-label="Menu">
        <span></span>
        <span></span>
        <span></span>
      </button>
    </div>
  </header>
</template>

<style scoped>
.nav-header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  padding: 1rem 2rem;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.nav-header.scrolled {
  background: rgba(10, 10, 15, 0.95);
  backdrop-filter: blur(20px);
  border-bottom: 1px solid rgba(100, 255, 218, 0.1);
  padding: 0.75rem 2rem;
  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.3);
}

.nav-container {
  max-width: 1400px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.nav-logo {
  text-decoration: none;
}

.logo-text {
  font-size: 1.5rem;
  font-weight: 800;
  background: linear-gradient(135deg, #64ffda 0%, #4a90e2 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.nav-links {
  display: flex;
  gap: 2rem;
}

.nav-link {
  color: #b0b0b0;
  text-decoration: none;
  font-size: 0.9375rem;
  font-weight: 500;
  transition: color 0.3s ease;
  position: relative;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 0;
  height: 2px;
  background: linear-gradient(90deg, #64ffda 0%, #4a90e2 100%);
  transition: width 0.3s ease;
}

.nav-link:hover {
  color: #64ffda;
}

.nav-link:hover::after {
  width: 100%;
}

.nav-actions {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.nav-resume-btn {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.625rem 1.25rem;
  background: transparent;
  border: 1px solid rgba(100, 255, 218, 0.4);
  border-radius: 6px;
  color: #64ffda;
  font-size: 0.875rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
}

.nav-resume-btn:hover {
  background: rgba(100, 255, 218, 0.1);
  border-color: #64ffda;
  transform: translateY(-2px);
}

.nav-resume-btn svg {
  transition: transform 0.3s ease;
}

.nav-resume-btn:hover svg {
  transform: translateY(2px);
}

.nav-hire-btn {
  padding: 0.625rem 1.5rem;
  background: linear-gradient(135deg, #64ffda 0%, #4fd1b0 100%);
  border-radius: 6px;
  color: #0f0f0f;
  font-size: 0.875rem;
  font-weight: 700;
  text-decoration: none;
  transition: all 0.3s ease;
  box-shadow: 0 2px 10px rgba(100, 255, 218, 0.3);
}

.nav-hire-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 20px rgba(100, 255, 218, 0.4);
}

.mobile-menu-btn {
  display: none;
  flex-direction: column;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 5px;
}

.mobile-menu-btn span {
  width: 24px;
  height: 2px;
  background: #64ffda;
  transition: all 0.3s ease;
}

@media (max-width: 968px) {
  .nav-links {
    display: none;
  }

  .nav-actions {
    display: none;
  }

  .mobile-menu-btn {
    display: flex;
  }
}

@media (max-width: 480px) {
  .nav-header {
    padding: 0.75rem 1rem;
  }

  .nav-header.scrolled {
    padding: 0.5rem 1rem;
  }
}
</style>
