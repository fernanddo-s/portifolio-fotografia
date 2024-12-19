<script setup lang="ts">
import Header from './components/Header.vue'
import HeroSection from './components/HeroSection.vue'
import Portfolio from './components/Portfolio.vue'
import AboutUs from './components/AboutUs.vue'
import ContactForm from './components/ContactForm.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <div class="min-h-screen">
    <Header />
    <main>
      <HeroSection />
      <Portfolio />
      <AboutUs />
      <ContactForm />
    </main>
    <Footer />
  </div>
</template>