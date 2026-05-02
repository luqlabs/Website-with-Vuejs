<script setup lang="ts">
import { ref, onMounted } from 'vue'
import { mockProducts } from '../mockData'
import ProductCarousel from '../components/ProductCarousel.vue'

const isLoading = ref(true)

onMounted(() => {
  // Simulate network request
  setTimeout(() => {
    isLoading.value = false
  }, 1000)
})
</script>

<template>
  <div class="w-full flex flex-col grow bg-white py-12">
    <div class="container mx-auto px-4 md:px-6">
      <div class="text-center mb-16">
        <h1 class="font-playfair text-4xl md:text-5xl font-semibold mb-4">All Products</h1>
        <p class="text-gray-600">Discover our complete collection of scientifically formulated skincare.</p>
      </div>

      <!-- Utilizing the existing ProductCarousel to show we can reuse components -->
      <ProductCarousel :products="mockProducts" :is-loading="isLoading" />
      
      <!-- Load More Button (Dummy) -->
      <div class="text-center mt-12">
        <button class="px-8 py-3 border border-black text-black text-sm uppercase tracking-wider font-medium hover:bg-black hover:text-white transition-colors">
          Load More
        </button>
      </div>
    </div>
  </div>
</template>
