<template>
  <section class="min-h-screen px-4 sm:px-8 md:px-16 lg:px-24 bg-[#222831] text-white flex items-center py-12">
    <div class="max-w-7xl mx-auto flex flex-col md:flex-row items-center justify-between gap-12">

      <!-- Left: Image -->
      <div class="w-full md:w-1/2 flex justify-center order-2 md:order-1">
        <img
          src="/images/burger.png"
          alt="Burger"
          class="w-64 sm:w-72 md:w-80 lg:max-w-sm object-contain"
        />
      </div>

      <!-- Right: Text Content -->
      <div class="w-full md:w-1/2 text-center md:text-left px-2 md:px-4 space-y-6 font-[Open_Sans] order-1 md:order-2">
        <h2 class="text-3xl font-[Dancing_Script] font-bold">
          We Are Feane
        </h2>
        <p class="text-base sm:text-lg leading-relaxed">
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
