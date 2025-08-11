<template>
  <div class="offers-section py-16 bg-[#f8f9fa]">
    <div class="container mx-auto px-4 pt-15">
      <div class="flex flex-col md:flex-row justify-center gap-10">
        <!-- Offer 1 -->
        <div
          class="bg-[#212529] rounded-xl p-6 w-full md:w-1/2 flex flex-col lg:flex-row items-center gap-6 group"
        >
          <div
            class="w-32 h-32 sm:w-40 sm:h-40 rounded-full border-4 border-yellow-400 overflow-hidden flex-shrink-0"
          >
            <img
              src="/images/o1.jpg"
              alt="Burger"
              class="w-full h-full object-cover transition-transform duration-300 ease-in-out group-hover:scale-110"
            />
          </div>
          <div class="text-white text-center lg:text-left">
            <h3 class="text-2xl sm:text-3xl font-semibold font-cursive pb-3.5">
              Tasty Thursdays
            </h3>
            <p class="text-3xl sm:text-4xl font-bold">
              20% <span class="text-lg align-bottom">off</span>
            </p>
            <button
              class="mt-4 cursor-pointer bg-yellow-400 text-white px-5 py-2 rounded-full flex items-center justify-center lg:justify-start gap-2 hover:bg-yellow-500 transition font-[Open_Sans]"
            >
              Order Now
              <i class="fas fa-shopping-cart"></i>
            </button>
          </div>
        </div>

        <!-- Offer 2 -->
        <div
          class="bg-[#212529] rounded-xl p-6 w-full md:w-1/2 flex flex-col lg:flex-row items-center gap-6 group"
        >
          <div
            class="w-32 h-32 sm:w-40 sm:h-40 rounded-full border-4 border-yellow-400 overflow-hidden flex-shrink-0"
          >
            <img
              src="/images/o2.jpg"
              alt="Pizza"
              class="w-full h-full object-cover transition-transform duration-300 ease-in-out group-hover:scale-110"
            />
          </div>
          <div class="text-white text-center lg:text-left">
            <h3 class="text-2xl sm:text-3xl font-semibold font-cursive pb-3.5">
              Pizza Days
            </h3>
            <p class="text-3xl sm:text-4xl font-bold">
              15% <span class="text-lg align-bottom">off</span>
            </p>
            <button
              class="mt-4 bg-yellow-400 text-white px-5 py-2 rounded-full flex items-center justify-center lg:justify-start gap-2 hover:bg-yellow-500 transition font-[Open_Sans]"
            >
              Order Now
              <i class="fas fa-shopping-cart"></i>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.font-cursive {
  font-family: 'Dancing Script', cursive;
}
</style>
