<script setup lang="ts">
import { Search, User, ShoppingBag, Menu } from 'lucide-vue-next'
</script>

<template>
  <div class="font-sans min-h-screen flex flex-col">
    <!-- Navbar (Exact Match to Next.js) -->
    <header class="sticky top-0 z-50 w-full border-b border-gray-200 bg-white/80 backdrop-blur-md">
      <div class="container mx-auto px-4 md:px-6 h-16 flex items-center justify-between">
        
        <!-- Mobile Menu & Search -->
        <div class="flex items-center gap-4 md:hidden">
          <button aria-label="Menu" class="text-gray-900 hover:text-gray-600 transition-colors">
            <Menu class="w-5 h-5" />
          </button>
          <button aria-label="Search" class="text-gray-900 hover:text-gray-600 transition-colors">
            <Search class="w-5 h-5" />
          </button>
        </div>

        <!-- Desktop Left Navigation -->
        <nav class="hidden md:flex items-center gap-8">
          <router-link to="/shop" class="text-sm font-medium uppercase tracking-wider text-gray-900 hover:text-gray-500 transition-colors">
            Shop
          </router-link>
          <router-link to="/story" class="text-sm font-medium uppercase tracking-wider text-gray-900 hover:text-gray-500 transition-colors">
            Our Story
          </router-link>
        </nav>

        <!-- Logo -->
        <div class="absolute left-1/2 -translate-x-1/2">
          <router-link to="/" class="font-playfair text-2xl font-bold tracking-widest text-gray-900">
            LUCKY
          </router-link>
        </div>

        <!-- Right Icons -->
        <div class="flex items-center gap-4 md:gap-6">
          <button aria-label="Search" class="hidden md:block text-gray-900 hover:text-gray-600 transition-colors">
            <Search class="w-5 h-5" />
          </button>
          
          <router-link to="/login" aria-label="Account" class="text-gray-900 hover:text-gray-600 transition-colors">
            <User class="w-5 h-5" />
          </router-link>

          <router-link to="/cart" aria-label="Cart" class="relative text-gray-900 hover:text-gray-600 transition-colors">
            <ShoppingBag class="w-5 h-5" />
            <span class="absolute -top-2 -right-2 bg-black text-white text-[10px] font-bold w-4 h-4 rounded-full flex items-center justify-center">
              0
            </span>
          </router-link>
        </div>
      </div>
    </header>

    <!-- Page Content Area -->
    <main class="grow flex flex-col relative">
      <router-view v-slot="{ Component }">
        <transition name="page" mode="out-in">
          <component :is="Component" />
        </transition>
      </router-view>
    </main>

    <!-- Footer -->
    <footer class="bg-gray-900 text-white py-16 mt-auto">
      <div class="container mx-auto px-4 md:px-6">
        <div class="grid grid-cols-1 md:grid-cols-4 gap-12">
          <div class="md:col-span-2">
            <span class="font-playfair text-2xl font-bold tracking-widest block mb-4">LUCKY</span>
            <p class="text-gray-400 text-sm max-w-sm">Premium skincare formulations focused on clinical efficacy and transparent pricing for the Jakarta market.</p>
          </div>
          <div>
            <h4 class="font-semibold mb-4 uppercase tracking-wider text-sm">Shop</h4>
            <ul class="space-y-2 text-gray-400 text-sm">
              <li><router-link to="/shop" class="hover:text-white transition-colors">All Products</router-link></li>
              <li><a href="#" class="hover:text-white transition-colors">Skincare</a></li>
              <li><a href="#" class="hover:text-white transition-colors">Bundles</a></li>
            </ul>
          </div>
          <div>
            <h4 class="font-semibold mb-4 uppercase tracking-wider text-sm">About</h4>
            <ul class="space-y-2 text-gray-400 text-sm">
              <li><router-link to="/story" class="hover:text-white transition-colors">Our Story</router-link></li>
              <li><a href="#" class="hover:text-white transition-colors">Ingredients</a></li>
              <li><a href="#" class="hover:text-white transition-colors">Contact</a></li>
            </ul>
          </div>
        </div>
        <div class="border-t border-gray-800 mt-16 pt-8 text-sm text-gray-500 text-center">
          &copy; 2026 LUCKY Skincare. All rights reserved. Vue 3 Prototype.
        </div>
      </div>
    </footer>
  </div>
</template>

<style>
/* Page Transition Animation */
.page-enter-active,
.page-leave-active {
  transition: opacity 0.3s ease, transform 0.3s ease;
}

.page-enter-from {
  opacity: 0;
  transform: translateY(10px);
}

.page-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>
