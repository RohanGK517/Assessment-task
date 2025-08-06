<template>
  <section class="mt-24 bg-[#222831] text-white pt-20 pb-16 px-4 sm:px-6 md:px-10 lg:px-20">
  <div class="max-w-7xl mx-auto flex flex-col md:flex-row items-center justify-between gap-12 mt-14">


      <!-- Left: Image -->
      <div class="w-full md:w-1/2 flex justify-center order-2 md:order-1 pt-7 pb-12">
        <img src="/images/burger.png" 
        alt="Burger" 
        class="w-60 sm:w-72 md:w-80 lg:max-w-sm object-contain" />
      </div>

      <!-- Right: Text Content -->
      <div class="w-full md:w-1/2 text-center md:text-left space-y-6 font-[Open_Sans] order-1 md:order-2">
        <h2 class="text-white text-3xl font-[Dancing_Script] font-bold">We Are Feane</h2>
        <p class="text-base sm:text-lg leading-relaxed text-white">
          There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration
          in some form, by injected humour, or randomised words which don't look even slightly believable.
          If you are going to use a passage of Lorem Ipsum, you need to be sure there isn't anything embarrassing
          hidden in the middle of text. All
        </p>
        <button
          class="bg-yellow-400 hover:bg-yellow-500 text-white font-semibold px-6 py-2 rounded-full transition-all duration-300"
        >
          Read More
        </button>
      </div>
    </div>
  </section>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Open+Sans&display=swap');
</style>
