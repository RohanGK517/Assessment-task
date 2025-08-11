<template>
  <section class="py-16 mb-24 bg-white ">
    <div class="max-w-screen-xl mx-auto px-4">
      <h2 class="text-4xl font-bold text-center mb-10 pt-20">Our Menu</h2>

      <!-- Category Filters -->
      <div class="flex justify-center gap-4 mb-10 flex-wrap font-[Open_Sans]">
        <button
          v-for="category in categories"
          :key="category"
          @click="selectedCategory = category"
          :class="[ 
            'px-5 py-2 rounded-full font-medium transition-all duration-300 cursor-pointer',
            selectedCategory === category
              ? 'bg-[#222831] text-white'
              : 'text-black hover:text-[#222831]'
          ]"
        >
          {{ category }}
        </button>
      </div>

      <!-- Cards Grid -->
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
        <transition-group name="fade" tag="div" class="contents">
          <div
            v-for="item in filteredItems"
            :key="item.id"
            class="flex justify-center"
          >
            <div
              class="menu-card w-full max-w-[350px] h-[490px] bg-[#222831] rounded-3xl overflow-hidden shadow-lg flex flex-col transition duration-300 cursor-pointer"
            >
              <!-- Top Half - Image Section -->
              <div
                class="bg-[#f1f2f3] h-1/2 rounded-bl-[40px] flex items-center justify-center relative z-10 overflow-hidden"
              >
                <img
                  :src="item.image"
                  alt="food"
                  class="menu-image w-[100%] h-[145px] object-contain transition-transform duration-300"
                />
              </div>

              <!-- Bottom Half - Content Section -->
              <div
                class="bg-[#222831] text-white h-1/2 px-5 py-4 flex flex-col justify-between"
              >
                <div>
                  <h3 class="text-lg font-bold mb-1 font-[Open_Sans]">
                    {{ item.title }}
                  </h3>
                  <p
                    class="text-sm text-gray-300 font-[Open_Sans] leading-snug"
                  >
                    {{ item.description }}
                  </p>
                </div>
                <div class="flex justify-between items-center mt-4">
                  <span class="text-gray-300 font-semibold text-lg font-[Open_Sans]">
                    ₹{{ item.price }}
                  </span>
                  <!-- <button
                    class="bg-yellow-500 text-white px-3 py-1.5 rounded-full hover:bg-yellow-600 transition"
                  >
                    <i class="fas fa-shopping-cart"></i>
                  </button> -->
                  <Addcart :dish="item" />
                </div>
              </div>
            </div>
          </div>
        </transition-group>
      </div>
<!-- 
      <button
        class="bg-yellow-400 hover:bg-yellow-500 text-white px-10 py-2.5 rounded-full font-[Open_Sans] transition-all duration-300 mt-10 mx-auto block mb-18"
      >
        View More
      </button> -->
       <BaseButton label="View More" @click="viewMore" extraClasses="mb-18" />
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue'

// ✅ Receive search term from parent (index.vue)
const props = defineProps({
  searchTerm: {
    type: String,
    default: ''
  }
})

const selectedCategory = ref('All')
const categories = ['All', 'Burger', 'Pizza', 'Pasta', 'Fries']

const allItems = [
  { id: 1, category: 'Burger', title: 'Chicken Burger', description: 'Juicy chicken burger with lettuce and cheese.', price: 120, image: '/images/menu-1.jpg' },
  { id: 2, category: 'Pizza', title: 'Pepperoni Pizza', description: 'Loaded with spicy pepperoni and extra cheese.', price: 200, image: '/images/menu-2.jpg' },
  { id: 3, category: 'Fries', title: 'French Fries', description: 'Crispy golden fries with ketchup.', price: 80, image: '/images/menu-3.jpg' },
  { id: 4, category: 'Pasta', title: 'Creamy Alfredo', description: 'Delicious creamy white sauce pasta.', price: 150, image: '/images/menu-4.jpg' },
  { id: 5, category: 'Pizza', title: 'Veggie Pizza', description: 'Fresh veggies topped over cheesy base.', price: 180, image: '/images/menu-5.jpg' },
  { id: 6, category: 'Burger', title: 'Cheese Burst Burger', description: 'Double cheese patty with onion rings.', price: 140, image: '/images/menu-6.jpg' },
  { id: 7, category: 'Pizza', title: 'Veg Loaded Pizza', description: 'Loaded with fresh vegetables and cheese.', price: 180, image: '/images/menu-7.jpg' },
  { id: 8, category: 'Pasta', title: 'Macaroni Cheese Pasta', description: 'Mac & cheese pasta with rich flavor.', price: 150, image: '/images/menu-4.jpg' }
]

const filteredItems = computed(() => {
  // Normalize search term for case-insensitive matching
  const term = props.searchTerm.trim().toLowerCase()

  return allItems.filter(item => {
    const matchesCategory = selectedCategory.value === 'All' || item.category === selectedCategory.value
    const matchesSearch = term === '' ||
      item.title.toLowerCase().includes(term) ||
      item.description.toLowerCase().includes(term)
    return matchesCategory && matchesSearch
  })
})
</script>
