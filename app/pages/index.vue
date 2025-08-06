<template>
  <div class="main"> 
    <NavBar />
    <div class="overlay">
      <Home />
     
    </div>
    
  </div>
  <div>
     <Offers />
     <Menu />
     <About />
      <Booking />
      <Reviews />
      <Footer />
  </div>

</template>

<script setup>
import NavBar from '@/components/NavBar.vue'
import Offers from '@/components/Offers.vue'
import Home from '@/components/Home.vue'
import Menu from '@/components/Menu.vue'
import About from '@/components/About.vue'  
import Booking from '@/components/Booking.vue'
import Reviews from '@/components/Reviews.vue'
import Footer from '@/components/Footer.vue'
</script>
<style scoped>
* {
  font-family: 'Dancing Script', sans-serif;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body, html {
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
