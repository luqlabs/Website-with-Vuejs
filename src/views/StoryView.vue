<script setup lang="ts">
// Our Story Page
</script>

<template>
  <div class="w-full flex flex-col grow bg-white">
    <div class="relative w-full h-[50vh] flex items-center justify-center overflow-hidden">
      <div class="absolute inset-0 z-0">
        <img 
          src="https://images.unsplash.com/photo-1617897903246-719242758050?auto=format&fit=crop&w=2000&q=80" 
          alt="Our Story" 
          class="w-full h-full object-cover object-center grayscale opacity-80"
        />
        <div class="absolute inset-0 bg-black/40"></div>
      </div>
      
      <div class="relative z-10 text-center px-4 max-w-3xl mx-auto">
        <h1 class="font-playfair text-5xl md:text-6xl text-white font-bold tracking-wider mb-4">
          Our Story
        </h1>
        <p class="text-white/90 text-lg font-light tracking-wide">
          Born in Jakarta, formulated for the world.
        </p>
      </div>
    </div>

    <div class="container mx-auto px-4 py-20 max-w-3xl text-center">
      <h2 class="font-playfair text-3xl font-semibold mb-6">Radical Transparency</h2>
      <p class="text-gray-600 leading-relaxed mb-8">
        LUCKY started with a simple question: why do clinically-effective skincare products have to cost so much? The answer was marketing, retail markups, and celebrity endorsements. We decided to strip all that away.
      </p>
      <p class="text-gray-600 leading-relaxed">
        Our focus is solely on what goes inside the bottle. High-quality ingredients, active formulations, and science-backed results. That's the LUCKY promise.
      </p>
    </div>
  </div>
</template>
