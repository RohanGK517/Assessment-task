<template>
  <section class="py-16 mt-32 sm:mt-24 md:mt-16 md:px-12 bg-white overflow-hidden pb-20">

    <div class="container mx-auto px-4 text-center">
      <h2 class="text-3xl sm:text-4xl font-[Dancing_Script] font-semibold mb-10 sm:mb-12">
        What Says Our Customers
      </h2>

      <!-- Swiper Slider -->
      <Swiper :modules="[Navigation]" :loop="true" :slides-per-view="1" :space-between="20" :breakpoints="{
        640: { slidesPerView: 1, spaceBetween: 20 },
        768: { slidesPerView: 2, spaceBetween: 30 }
      }" :navigation="{
        nextEl: '#swiper-next',
        prevEl: '#swiper-prev'
      }" class="w-full px-2 sm:px-4">
        <SwiperSlide v-for="(review, index) in reviews" :key="index">
          <div class="flex flex-col items-start font-[Open_Sans] px-4">
            <div class="bg-[#212529] text-white p-6 rounded-md w-full max-w-md sm:max-w-lg lg:max-w-[44rem] mx-auto">
              <p class="text-left mb-4 text-sm sm:text-base">{{ review.text }}</p>
              <h3 class="text-left font-semibold text-base sm:text-lg">{{ review.name }}</h3>
              <p class="text-left text-xs sm:text-sm">{{ review.detail }}</p>
            </div>

            <div class="relative mt-6">
              <!-- Arrow pointing to the image -->
              <div
                class="absolute left-10 -top-3 w-0 h-0 border-l-[15px] border-l-transparent border-r-[15px] border-r-transparent border-b-[15px] border-b-[#fbbf24] z-10">
              </div>

              <!-- Reviewer Image -->
              <img :src="review.image" alt="Reviewer image"
                class="relative rounded-full border-[5px] border-[#fbbf24] w-24 h-24 sm:w-28 sm:h-28 object-cover" />
            </div>
          </div>
        </SwiperSlide>

      </Swiper>

      <!-- Custom Navigation Arrows -->
      <div class="flex justify-center gap-4 mt-10 sm:mt-12 flex-wrap mb-16">
        <button id="swiper-prev"
          class="bg-yellow-400 text-white h-12 w-12 cursor-pointer rounded-full hover:bg-yellow-500 transition duration-300">
          <i class="fa-solid fa-angle-left"></i>
        </button>
        <button id="swiper-next"
          class="bg-yellow-400 text-white h-12 w-12 cursor-pointer rounded-full hover:bg-yellow-500 transition duration-300">
          <i class="fa-solid fa-angle-right"></i>
        </button>
      </div>
    </div>
  </section>
</template>


<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Navigation } from 'swiper/modules'
import 'swiper/css'
import 'swiper/css/navigation'

const reviews = [
  {
    text:
      'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
    name: 'Moana Michell',
    detail: 'magna aliqua',
    image: '/images/user1.png',
  },
  {
    text:
      'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
    name: 'Mike Hamell',
    detail: 'magna aliqua',
    image: '/images/user2.png',
  },
  {
    text:
      'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
    name: 'Moana Michell',
    detail: 'magna aliqua',
    image: '/images/user1.png',
  },
  {
    text:
      'Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
    name: 'Mike Hamell',
    detail: 'magna aliqua',
    image: '/images/user2.png',
  },
]
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600&display=swap');
</style>
