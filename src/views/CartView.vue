<script setup lang="ts">
// Cart Page logic
</script>

<template>
  <div class="w-full flex flex-col grow bg-white py-12">
    <div class="container mx-auto px-4 md:px-6 max-w-4xl">
      <h1 class="font-playfair text-4xl font-semibold mb-8 border-b border-gray-200 pb-4">Your Cart</h1>
      
      <div class="text-center py-20 bg-gray-50 border border-dashed border-gray-300">
        <h2 class="text-xl font-medium text-gray-600 mb-4">Your cart is currently empty</h2>
        <router-link to="/shop" class="inline-block px-8 py-3 bg-black text-white text-sm uppercase tracking-wider font-medium hover:bg-gray-800 transition-colors">
          Continue Shopping
        </router-link>
      </div>
    </div>
  </div>
</template>
