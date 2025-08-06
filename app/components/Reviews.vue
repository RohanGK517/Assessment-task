<template>
  <section class="py-16 bg-white">
    <div class="container mx-auto px-4 text-center md:pt-9">
      <h2 class="text-4xl font-[Dancing_Script] font-semibold mb-12">What Says Our Customers</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-10 font-[Open_Sans]">
        <div v-for="(review, index) in reviews" :key="index" class="flex flex-col items-center">
          <div class="bg-[#212529] text-white p-6 rounded-md max-w-lg w-full">
            <p class="text-left mb-4">{{ review.text }}</p>
            <h3 class="text-left font-semibold text-lg">{{ review.name }}</h3>
            <p class="text-left text-sm">{{ review.detail }}</p>
          </div>
          <div class="relative mt-6 pr-90">
            <div class="relative left-1/2 transform -translate-x-1/2 -top-3 w-0 h-0 border-l-[15px] border-l-transparent border-r-[15px] border-r-transparent border-b-[15px] border-b-[#fbbf24] z-10"></div>
            <img :src="review.image" alt="" class="relative rounded-full border-[5px] border-[#fbbf24] w-28 h-28 object-cover mt-[-13.5px]">
          </div>
        </div>
      </div>
      <div class="flex justify-center gap-4 mt-10 mb-10">
        <button class="bg-[#fbbf24] hover:bg-yellow-400 text-white rounded-full w-12 h-12 text-xl">←</button>
        <button class="bg-[#fbbf24] hover:bg-yellow-400 text-white rounded-full w-12 h-12 text-xl">→</button>
      </div>
    </div>
  </section>
</template>

<script setup>
const reviews = [
  {
    text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam',
    name: 'Moana Michell',
    detail: 'magna aliqua',
    image: '/images/user1.png'
  },
  {
    text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam',
    name: 'Mike Hamell',
    detail: 'magna aliqua',
    image: '/images/user2.png'
  }
];
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600&display=swap');
</style>
