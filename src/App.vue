<script setup>
import NavHeader from './components/NavHeader.vue'
import HeroSection from './components/HeroSection.vue'
import QuickHighlights from './components/QuickHighlights.vue'
import ValueProposition from './components/ValueProposition.vue'
import ExperienceSection from './components/ExperienceSection.vue'
import CaseStudies from './components/CaseStudies.vue'
import SkillsSection from './components/SkillsSection.vue'
import WhyHireMe from './components/WhyHireMe.vue'
import ContactSection from './components/ContactSection.vue'

// Customize these values with your information
const personalInfo = {
  name: 'Awanish Kumar',
  email: 'Awanish131@gmail.com',
  linkedin: 'https://www.linkedin.com/in/awanish-kumar-1189499b/',
  github: 'https://github.com/yourusername'
}
</script>

<template>
  <NavHeader />
  <main class="portfolio">
    <HeroSection :name="personalInfo.name" />
    <QuickHighlights />
    <ValueProposition />
    <CaseStudies />
    <SkillsSection />
    <ExperienceSection />
    <WhyHireMe />
    <ContactSection
      :email="personalInfo.email"
      :linkedin="personalInfo.linkedin"
      :github="personalInfo.github"
    />
  </main>
</template>

<style scoped>
.portfolio {
  width: 100%;
}
</style>
