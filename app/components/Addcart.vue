<!-- components/CartButton.vue -->
<template>
  <button
    @click="handleAddToCart"
    class="bg-yellow-500 text-white px-3 py-1.5 rounded-full hover:bg-yellow-600 transition cursor-pointer"
  >
    <i class="fas fa-shopping-cart"></i>
  </button>
</template>

<script setup>
const props = defineProps({
  dish: Object, // expects { id, title, price, image, description }
})

const cart = useState('cart', () => [])
const router = useRouter()

const handleAddToCart = () => {
  cart.value.push({ ...props.dish })
  router.push('/cart')
}
</script>
