<template>
  <div class="w-full h-[90vh] relative overflow-hidden">
    <Swiper
      :modules="[Autoplay, Pagination]"
      :loop="true"
      :autoplay="{ delay: 4000, disableOnInteraction: false }"
      :pagination="{ clickable: true }"
      class="h-full swiper-custom"
    >
      <SwiperSlide v-for="n in totalSlides" :key="n">
        <div
          class="relative w-full h-full"
        >
          <!-- Text content -->
          <div
            class="absolute top-[6%] md:top-[10%] left-4 md:left-28 max-w-lg text-white z-10 px-4 md:px-0"
          >
            <h1
              class="text-2xl sm:text-3xl md:text-5xl font-bold font-['Dancing_Script'] mb-4"
            >
              Fast Food Restaurant
            </h1>
            <p class="text-sm sm:text-base font-['Open_Sans'] mb-6">
              Doloremque, itaque aperiam facilis rerum, commodi, temporibus
              sapiente ad mollitia laborum quam quisquam esse error unde.
              Tempora ex doloremque, labore, sunt repellat dolore, iste magni
              quos nihil ducimus libero ipsam.
            </p>
            <button
              class="bg-[#ffbe33] font-['Open_Sans'] text-white px-6 py-2 rounded-full text-sm md:text-base hover:bg-[#e88e00] transition"
            >
              Order Now
            </button>
          </div>
        </div>
      </SwiperSlide>
    </Swiper>
  </div>
</template>

<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Autoplay, Pagination } from 'swiper/modules'
import 'swiper/css'
import 'swiper/css/pagination'

const totalSlides = 3
</script>

<style scoped>
:deep(.swiper-pagination-bullet) {
  background-color: white;
  opacity: 0.6;
  width: 10px;
  height: 10px;
  margin: 0 4px;
}

:deep(.swiper-pagination-bullet-active) {
  background-color: #ffbe33;
  opacity: 1;
}

:deep(.swiper-pagination) {
  bottom: 20px !important;
  z-index: 30;
}
</style>

<style>

html,
body {
  overflow-x: hidden;
}
</style>
