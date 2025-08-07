<template>
  <div class="bg-white min-h-screen flex items-center justify-center px-6 pt-16 md:pt-24 md:px-12">
    <div class="max-w-7xl w-full grid md:grid-cols-2 gap-8 items-center mt-15 ml-5 mr-4">
      <!-- Left Form -->
      <div>
        <h2 class="text-[40px] title-font font-extrabold mb-6">Book A Table</h2>

        <form class="space-y-4 font-[Open_Sans]">
          <input type="text" placeholder="Your Name"
            class="w-full border border-gray-300 rounded px-4 py-3 focus:outline-none focus:ring-2 focus:ring-yellow-300" />
          <input type="text" placeholder="Phone Number"
            class="w-full border border-gray-300 rounded px-4 py-3 focus:outline-none focus:ring-2 focus:ring-yellow-300" />
          <input type="email" placeholder="Your Email"
            class="w-full border border-gray-300 rounded px-4 py-3 focus:outline-none focus:ring-2 focus:ring-yellow-300" />

          <select
            class="w-full border border-gray-300 font-[Open_Sans] rounded px-4 py-3 focus:outline-none focus:ring-2 focus:ring-yellow-300">
            <option>How many persons?</option>
            <option>1 Person</option>
            <option>2 People</option>
            <option>3 People</option>
            <option>4+ People</option>
          </select>

          <input type="date"
            class="w-full border border-gray-300 rounded px-4 py-3 focus:outline-none focus:ring-2 focus:ring-yellow-300"
            placeholder="dd-mm-yyyy" />

          <button type="submit"
            class="bg-yellow-400 hover:bg-yellow-500 text-white font-semibold py-2.5 px-16 rounded-full mt-4">
            BOOK NOW
          </button>
        </form>
      </div>

      <!-- Right Map -->
      <div class="rounded-lg overflow-hidden shadow-md w-full h-[300px] mr-6">
        <iframe
          src="https://www.google.com/maps/embed?pb=!1m14!1m12!1m3!1d15554.33360246679!2d77.61924415!3d12.934475849999998!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!5e0!3m2!1sen!2sin!4v1754308986478!5m2!1sen!2sin"
          width="100%" height="100%" style="border:0;" allowfullscreen="" loading="lazy"
          referrerpolicy="no-referrer-when-downgrade"></iframe>
      </div>
    </div>
    <div class="mb-24"></div>
  </div>
</template>

<script setup>
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&display=swap');

.title-font {
  font-family: 'Dancing Script', cursive;
}
</style>
