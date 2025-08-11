<template>
    <NavBar />
  <div class="max-w-screen-xl mx-auto px-4 py-16">
    <h1 class="text-4xl font-bold mb-10 text-center">Your Cart</h1>

    <div v-if="cart &&Object.keys(cart).length === 0" class="text-center text-lg text-gray-600">
      Your cart is empty. <NuxtLink to="menu" class="text-yellow-500 underline">Go to menu</NuxtLink>
    </div>

    <div v-else>
      <div class="space-y-6 mb-10">
        <div
          v-for="(item, index) in cart"
          :key="index"
          class="flex justify-between items-center bg-gray-100 p-4 rounded-lg"
        >
          <div>
            <h3 class="text-xl font-semibold">{{ item.title }}</h3>
            <p class="text-sm text-gray-600">₹{{ item.price }}</p>
          </div>
          <img
            :src="item.image"
            alt="item"
            class="w-20 h-20 object-cover rounded"
          />
        </div>
      </div>

      <div class="text-right text-2xl font-bold">
        Total: ₹{{ totalPrice }}
      </div>
    </div>
  </div>
</template>

<script setup>
const cart = useState('cart')

const totalPrice = computed(() =>
  cart.value ? cart.value.reduce((sum, item) => sum + item.price, 0) : 0
)
</script>

