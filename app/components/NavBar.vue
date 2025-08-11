<template>
  <nav class="navbar">
    <div class="nav-container">
      <a href="/">
        <div class="logo">Feane</div>
      </a>

      <!-- Hamburger Icon -->
      <div class="hamburger" @click="toggleMenu">
        <i :class="menuOpen ? 'fas fa-times' : 'fas fa-bars'"></i>
      </div>

      <!-- Nav Links -->
      <ul :class="['nav-links', menuOpen ? 'show' : '']">
        <li>
          <NuxtLink to="/" :class="{ active: route.path === '/' }">HOME</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/menu" :class="{ active: route.path === '/menu' }">MENU</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/about" :class="{ active: route.path === '/about' }">ABOUT</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/booking" :class="{ active: route.path === '/booking' }">BOOK TABLE</NuxtLink>
        </li>
      </ul>


      <!-- Inside nav-icons -->
      <div :class="['nav-icons', menuOpen ? 'show-icons' : '']">
        <i class="fas fa-user"></i>
        <NuxtLink to="/cart" :class="{ active: route.path === '/cart' }">
          <i class="fas fa-shopping-cart"></i>
        </NuxtLink>

        <!-- Search -->
        <div class="relative">
          <i class="fas fa-search cursor-pointer" @click="toggleSearch"></i>
          <input v-if="showSearch" v-model="searchQuery" @input="emitSearch" type="text" placeholder="Search food..."
            class="absolute top-full mt-10 px-2 py-1 text-[#e6ac00] text-xl rounded" />
        </div>

        <NuxtLink to="/menu" :class="{ active: route.path === '/menu' }"><button class="order-btn">Order Online</button>
        </NuxtLink>
      </div>

    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue'
const menuOpen = ref(false)
const toggleMenu = () => {
  menuOpen.value = !menuOpen.value
}

const route = useRoute()

const showSearch = ref(false)
const searchQuery = ref('')
const emit = defineEmits(['search'])

const toggleSearch = () => {
  showSearch.value = !showSearch.value
}

const emitSearch = () => {
  emit('search', searchQuery.value)
}
</script>



<style scoped>
.navbar {
  position: sticky;
  top: 0;
  z-index: 1000;
  background: linear-gradient(to right, #0f0f0f, #464646);
  font-family: 'Poppins', sans-serif;
  padding: 16px 0;
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;

  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  position: relative;
}

.logo {
  font-family: 'Dancing Script', cursive;
  color: white;
  font-size: 32px;
  font-weight: bold;
}

.hamburger {
  display: none;
  font-size: 24px;
  color: white;
  cursor: pointer;
}

/* Default Nav Links */
.nav-links {
  list-style: none;
  display: flex;
  gap: 30px;
  margin: 0;
  padding: 0;
}

.nav-links a {
  color: white;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
}

.nav-links a.active,
.nav-links a:hover {
  color: orange;
}

.nav-icons {
  display: flex;
  align-items: center;
  gap: 20px;
}

.nav-icons i {
  color: white;
  font-size: 18px;
  cursor: pointer;
  transition: color 0.3s;
}

.nav-icons i:hover {
  color: orange;
}

.order-btn {
  padding: 8px 24px;
  background-color: #ffbe33;
  font-family: 'Open Sans', sans-serif;
  color: white;
  border: none;
  border-radius: 45px;
  font-size: 1rem;
  width: 160px;
  cursor: pointer;
  transition: background-color 0.3s ease, transform 0.2s ease;
}

.order-btn:hover {
  background-color: #e6ac00;
}

@media (max-width: 1024px) {
  .hamburger {
    display: block;
  }

  .nav-links {
    flex-direction: column;
    width: 100%;
    display: none;
    margin-top: 20px;
    gap: 15px;
    align-items: center;
  }

  .nav-links.show {
    display: flex;
  }

  .nav-icons {
    display: none;
    flex-direction: column;
    align-items: flex-start;
    width: 100%;
    gap: 15px;
    margin-top: 15px;
    align-items: center;
  }

  .nav-icons.show-icons {
    display: flex;
  }

  .order-btn {
    margin-top: 10px;
  }
}
</style>
