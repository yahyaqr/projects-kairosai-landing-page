<template>
  <div class="min-h-screen bg-[#0A0A0A] text-gray-300 font-sans overflow-hidden">
    <Navbar :scrolled="scrolled" />
    <HeroSection />
    <HowItWorksSection />
    <FeaturesSection />
    <UseCasesSection />
    <IntegrationSection />
    <PricingSection />
    <TestimonialsSection />
    <FAQSection />
    <CTASection />
    <Footer />
  </div>
</template>

<script setup>
import { ref } from 'vue'
import Navbar from './components/Navbar.vue'
import HeroSection from './components/HeroSection.vue'
import HowItWorksSection from './components/HowItWorksSection.vue'
import FeaturesSection from './components/FeaturesSection.vue'
import UseCasesSection from './components/UseCasesSection.vue'
import IntegrationSection from './components/IntegrationSection.vue'
import PricingSection from './components/PricingSection.vue'
import TestimonialsSection from './components/TestimonialsSection.vue'
import FAQSection from './components/FAQSection.vue'
import CTASection from './components/CTASection.vue'
import Footer from './components/Footer.vue'

const scrolled = ref(false);
</script>

<style scoped>
/* Global styles can go here if necessary */
</style>
