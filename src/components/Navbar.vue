<template>
  <nav class="fixed top-0 left-0 w-full z-50 bg-[#F5F5F4] shadow-md">
    <div class="max-w-7xl mx-auto px-6 py-4 flex items-center justify-between">
      <div class="text-2xl font-display text-[#333]">
        K☕️pi Santai!
      </div>

      <div class="hidden md:flex space-x-8">
        <a v-for="link in links" :key="link.name" :href="link.href" class="text-[#777] hover:text-[#C4A484] transition">
          {{ link.name }}
        </a>
      </div>

      <!-- Mobile Hamburger -->
      <div class="md:hidden">
        <button @click="menuOpen = !menuOpen" class="focus:outline-none">
          <svg v-if="!menuOpen" xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-[#333]" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
          </svg>
          <svg v-else xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-[#333]" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
          </svg>
        </button>
      </div>
    </div>

    <!-- Mobile Menu -->
    <div v-if="menuOpen" class="md:hidden bg-[#F5F5F4] flex flex-col items-center py-4 space-y-4">
      <a v-for="link in links" :key="link.name" :href="link.href" @click="menuOpen = false" class="text-[#777] hover:text-[#C4A484] transition">
        {{ link.name }}
      </a>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue'

const menuOpen = ref(false)

const links = [
  { name: 'Home', href: '#home' },
  { name: 'About', href: '#about' },
  { name: 'Menu', href: '#menu' },
  { name: 'Gallery', href: '#gallery' },
  { name: 'Testimonials', href: '#testimonials' },
  { name: 'Contact', href: '#contact' },
]
</script>

<style scoped>
/* Smooth scroll */
html {
  scroll-behavior: smooth;
}
</style>
