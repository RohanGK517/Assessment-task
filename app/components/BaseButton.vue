<template>
  <button
    :class="[
      'bg-yellow-400 hover:bg-yellow-500 text-white px-10 py-2.5 rounded-full font-[Open_Sans] transition-all duration-300 mt-10 mx-auto block',
      extraClasses
    ]"
    @click="$emit('click')"
  >
    {{ label }}
  </button>
</template>

<script setup>
const props = defineProps({
  label: { type: String, required: true },        // Button text
  extraClasses: { type: String, default: '' }     // Optional extra Tailwind classes
});

const emit = defineEmits(['click']);
</script>
