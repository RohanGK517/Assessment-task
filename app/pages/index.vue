<template>
  <!-- Hero Section -->
  <div class="main">
    <NavBar @search="searchTerm = $event" />
    <div class="overlay">
      <Home />
    </div>
  </div>

  <!-- Wrapped sections -->
  <div class="section-container py-16">
    <Offers />
  </div>

  <div class="section-container py-16">
    <Menu :searchTerm="searchTerm" />
  </div>

  <section class="full-width-section bg-[#222831] py-16">
    <div class="section-container">
      <About />
    </div>
  </section>

  <div class="section-container py-16">
    <Booking />
  </div>

  <div class="section-container py-16">
    <Reviews />
  </div>

  <footer class="full-width-section bg-[#222831] text-white pt-16">
    <div class="section-container">
      <Footer />
    </div>
  </footer>
</template>

<script setup>
import { ref } from 'vue'
import NavBar from '@/components/NavBar.vue'
import Offers from '@/components/Offers.vue'
import Home from '@/components/Home.vue'
import Menu from '@/components/Menu.vue'
import About from '@/components/About.vue'
import Booking from '@/components/Booking.vue'
import Reviews from '@/components/Reviews.vue'
import Footer from '@/components/Footer.vue'

// Reactive search term from navbar
const searchTerm = ref('')
</script>

<style scoped>
* {
  font-family: 'Dancing Script', sans-serif;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body,
html {
  overflow-x: hidden;
}

.main {
  background: url('/images/hero-bg.jpg') no-repeat center center;
  background-size: cover;
  height: 100vh;
  width: 100%;
  position: relative;
  overflow: hidden;
}

.overlay {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 2rem 1rem;
  position: relative;
  overflow-x: hidden;
}

.section-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.full-width-section {
  width: 100%;
}

@media (min-width: 768px) {
  .overlay {
    padding-left: 5rem;
    padding-top: 6rem;
    align-items: flex-start;
  }
}

@media (min-width: 1024px) {
  .overlay {
    padding-left: 6rem;
    padding-top: 7rem;
  }
}
</style>
