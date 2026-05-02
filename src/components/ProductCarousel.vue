<script setup lang="ts">
import { ref } from 'vue'
import type { Product } from './mockData'

const props = defineProps<{
  products: Product[]
  isLoading?: boolean
}>()

const formatIdr = (val: number) => {
  return new Intl.NumberFormat('id-ID', {
    style: 'currency',
    currency: 'IDR',
    minimumFractionDigits: 0
  }).format(val)
}
</script>

<template>
  <div class="grid grid-cols-1 md:grid-cols-3 lg:grid-cols-3 gap-6 pb-8">
    
    <!-- SKELETON LOADER -->
    <template v-if="isLoading">
      <div v-for="i in 3" :key="i" class="flex flex-col gap-4">
        <div class="w-full aspect-[4/5] shimmer bg-gray-100"></div>
        <div class="mt-4 flex flex-col gap-1">
          <div class="h-3 w-1/4 shimmer mt-1"></div>
          <div class="h-5 w-3/4 shimmer mt-1"></div>
          <div class="h-4 w-1/3 shimmer mt-1"></div>
        </div>
      </div>
    </template>

    <!-- ACTUAL PRODUCTS -->
    <template v-else>
      <a 
        v-for="product in products" 
        :key="product.id"
        href="#"
        class="group cursor-pointer block"
      >
        <div class="relative bg-gray-100 aspect-[4/5] mb-4 overflow-hidden">
          <img 
            :src="product.image_url" 
            :alt="product.product_name" 
            class="w-full h-full object-cover object-center group-hover:scale-105 transition-transform duration-700 ease-in-out"
            loading="lazy"
          />
          <div class="absolute top-4 left-4 bg-white/90 backdrop-blur-sm px-3 py-1 text-xs font-bold uppercase tracking-wider">
            {{ product.category }}
          </div>
        </div>
        
        <div class="mt-4 flex flex-col gap-1 text-left">
          <span class="text-xs text-gray-500 font-medium tracking-widest uppercase">{{ product.brand }}</span>
          <h3 class="text-lg font-medium text-gray-900 group-hover:underline underline-offset-4 decoration-1">
            {{ product.product_name }}
          </h3>
          <p class="text-sm font-semibold mt-1">{{ formatIdr(product.our_price_idr) }}</p>
        </div>
      </a>
    </template>
  </div>
</template>
