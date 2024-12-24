<script setup lang="ts">
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import ProductSection from './components/ProductSection.vue'
import Testimonials from './components/Testimonials.vue'
import Footer from './components/Footer.vue'
import WhatsAppButton from './components/WhatsAppButton.vue'
</script>

<template>
  <div class="min-h-screen">
    <Header />
    <main>
      <Hero />
      <ProductSection />
      <Testimonials />
    </main>
    <Footer />
    <WhatsAppButton/>
  </div>
</template>