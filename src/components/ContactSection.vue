<script setup>
defineProps({
  email: {
    type: String,
    default: 'awanish1311@gmail.com'
  },
  linkedin: {
    type: String,
    default: 'https://www.linkedin.com/in/awanish-kumar-1189499b/'
  },
  github: {
    type: String,
    default: 'https://github.com/yourusername'
  }
})
</script>

<template>
  <section id="contact" class="contact">
    <div class="container">
      <h2 class="section-title">Ready to Hire?</h2>
      <p class="contact-intro">
        Looking for a senior full-stack engineer who ships production code from day one?
        I'm open to product engineering roles and remote positions. Currently available for immediate joining.
      </p>

      <div class="contact-links">
        <a :href="`mailto:${email}`" class="contact-link">
          <span class="link-label">Email</span>
          <span class="link-value">{{ email }}</span>
        </a>

        <a :href="linkedin" target="_blank" rel="noopener noreferrer" class="contact-link">
          <span class="link-label">LinkedIn</span>
          <span class="link-value">Connect with me</span>
        </a>

        <a :href="github" target="_blank" rel="noopener noreferrer" class="contact-link">
          <span class="link-label">GitHub</span>
          <span class="link-value">View my code</span>
        </a>
      </div>

      <div class="availability">
        <div class="status-indicator"></div>
        <span>Available for immediate joining</span>
      </div>

      <div class="cta-urgency">
        <p class="urgency-text">
          <strong>Let's discuss how I can help your team.</strong>
          <br>
          Response time: Usually within 24 hours
        </p>
        <a :href="`mailto:${email}?subject=Job Opportunity - Full Stack Developer&body=Hi Awanish,%0D%0A%0D%0AI came across your portfolio and I'd like to discuss a potential opportunity.%0D%0A%0D%0A`" class="cta-email-btn">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none">
            <path d="M3 8L10.89 13.26C11.2187 13.4793 11.6049 13.5963 12 13.5963C12.3951 13.5963 12.7813 13.4793 13.11 13.26L21 8M5 19H19C19.5304 19 20.0391 18.7893 20.4142 18.4142C20.7893 18.0391 21 17.5304 21 17V7C21 6.46957 20.7893 5.96086 20.4142 5.58579C20.0391 5.21071 19.5304 5 19 5H5C4.46957 5 3.96086 5.21071 3.58579 5.58579C3.21071 5.96086 3 6.46957 3 7V17C3 17.5304 3.21071 18.0391 3.58579 18.4142C3.96086 18.7893 4.46957 19 5 19Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
          <span>Send Me an Email</span>
        </a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact {
  position: relative;
  padding: 6rem 2rem;
  background: linear-gradient(135deg, #16213e 0%, #0a0a0f 50%, #1a1a2e 100%);
  overflow: hidden;
}

.contact::before {
  content: '';
  position: absolute;
  bottom: -200px;
  right: -200px;
  width: 500px;
  height: 500px;
  background: radial-gradient(circle, rgba(100, 255, 218, 0.15) 0%, transparent 70%);
  filter: blur(80px);
  pointer-events: none;
}

.contact::after {
  content: '';
  position: absolute;
  top: -150px;
  left: -150px;
  width: 400px;
  height: 400px;
  background: radial-gradient(circle, rgba(74, 144, 226, 0.1) 0%, transparent 70%);
  filter: blur(80px);
  pointer-events: none;
}

.container {
  position: relative;
  max-width: 650px;
  margin: 0 auto;
  text-align: center;
  z-index: 1;
}

.section-title {
  font-size: 2.75rem;
  font-weight: 700;
  margin: 0 0 1.5rem;
  background: linear-gradient(135deg, #ffffff 0%, #64ffda 50%, #4a90e2 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.contact-intro {
  font-size: 1.125rem;
  color: #b0b0b0;
  line-height: 1.8;
  margin: 0 0 3rem;
}

.contact-links {
  display: flex;
  flex-direction: column;
  gap: 1.25rem;
  margin-bottom: 3rem;
}

.contact-link {
  position: relative;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: linear-gradient(135deg, rgba(26, 26, 46, 0.6) 0%, rgba(20, 20, 35, 0.6) 100%);
  backdrop-filter: blur(15px);
  border: 1px solid rgba(100, 255, 218, 0.15);
  border-radius: 12px;
  padding: 1.25rem 1.75rem;
  text-decoration: none;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  overflow: hidden;
}

.contact-link::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  width: 4px;
  background: linear-gradient(180deg, #64ffda 0%, #4a90e2 100%);
  transform: scaleY(0);
  transform-origin: bottom;
  transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

.contact-link::after {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, rgba(100, 255, 218, 0.05) 0%, transparent 100%);
  opacity: 0;
  transition: opacity 0.4s ease;
}

.contact-link:hover {
  border-color: rgba(100, 255, 218, 0.4);
  transform: translateX(8px);
  box-shadow:
    0 12px 24px rgba(0, 0, 0, 0.3),
    0 0 20px rgba(100, 255, 218, 0.15);
}

.contact-link:hover::before {
  transform: scaleY(1);
  transform-origin: top;
}

.contact-link:hover::after {
  opacity: 1;
}

.link-label {
  position: relative;
  z-index: 1;
  font-size: 0.875rem;
  font-weight: 600;
  color: #808080;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  transition: color 0.3s ease;
}

.contact-link:hover .link-label {
  color: #64ffda;
}

.link-value {
  position: relative;
  z-index: 1;
  font-size: 1rem;
  color: #64ffda;
  font-weight: 500;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.link-value::after {
  content: '→';
  font-size: 1.25rem;
  opacity: 0;
  transform: translateX(-10px);
  transition: all 0.3s ease;
}

.contact-link:hover .link-value::after {
  opacity: 1;
  transform: translateX(0);
}

.availability {
  display: inline-flex;
  align-items: center;
  gap: 0.875rem;
  background: linear-gradient(135deg, rgba(100, 255, 218, 0.15) 0%, rgba(74, 144, 226, 0.1) 100%);
  backdrop-filter: blur(10px);
  border: 2px solid rgba(100, 255, 218, 0.3);
  border-radius: 50px;
  padding: 1rem 2rem;
  font-size: 1rem;
  color: #64ffda;
  font-weight: 500;
  box-shadow: 0 8px 16px rgba(100, 255, 218, 0.1);
  transition: all 0.3s ease;
}

.availability:hover {
  transform: scale(1.05);
  box-shadow: 0 12px 24px rgba(100, 255, 218, 0.2);
}

.status-indicator {
  width: 12px;
  height: 12px;
  background: #64ffda;
  border-radius: 50%;
  box-shadow: 0 0 10px rgba(100, 255, 218, 0.6);
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0%, 100% {
    opacity: 1;
    transform: scale(1);
    box-shadow: 0 0 10px rgba(100, 255, 218, 0.6);
  }
  50% {
    opacity: 0.7;
    transform: scale(1.1);
    box-shadow: 0 0 20px rgba(100, 255, 218, 0.8);
  }
}

.cta-urgency {
  margin-top: 3rem;
  padding: 2rem;
  background: linear-gradient(135deg, rgba(100, 255, 218, 0.08) 0%, rgba(74, 144, 226, 0.05) 100%);
  border: 1px solid rgba(100, 255, 218, 0.2);
  border-radius: 16px;
}

.urgency-text {
  font-size: 1rem;
  color: #b0b0b0;
  line-height: 1.8;
  margin: 0 0 1.5rem;
}

.urgency-text strong {
  color: #ffffff;
  font-size: 1.125rem;
}

.cta-email-btn {
  display: inline-flex;
  align-items: center;
  gap: 0.75rem;
  padding: 1rem 2rem;
  background: linear-gradient(135deg, #64ffda 0%, #4fd1b0 100%);
  border-radius: 10px;
  color: #0f0f0f;
  font-size: 1rem;
  font-weight: 700;
  text-decoration: none;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  box-shadow: 0 4px 15px rgba(100, 255, 218, 0.3);
}

.cta-email-btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 25px rgba(100, 255, 218, 0.5);
}

.cta-email-btn svg {
  transition: transform 0.3s ease;
}

.cta-email-btn:hover svg {
  transform: scale(1.1);
}

@media (max-width: 768px) {
  .section-title {
    font-size: 2.25rem;
  }

  .contact-link:hover {
    transform: translateX(4px);
  }

  .cta-urgency {
    padding: 1.5rem;
  }
}
</style>
