<template>
  <section id="gallery" class="py-16 bg-white px-6">
    <div class="max-w-6xl mx-auto text-center">
      <h2 class="font-display text-4xl text-[#333] mb-12">Galeri</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div v-for="(image, index) in images" :key="index" class="overflow-hidden rounded-2xl shadow-md hover:scale-105 transition-transform duration-300">
          <img :src="image" alt="Gallery Image" class="w-full h-64 object-cover" />
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const images = [
  '/gallery/gallery1.jpg',
  '/gallery/gallery2.jpg',
  '/gallery/gallery3.jpg',
  '/gallery/gallery4.jpg',
  '/gallery/gallery5.jpg',
  '/gallery/gallery6.jpg'
]
</script>
