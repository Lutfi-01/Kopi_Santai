<template>
  <section id="testimonials" class="bg-cream py-16 px-8 text-center">
    <h2 class="font-display text-4xl text-[#333] mb-12">Testimoni</h2>
    <Carousel
  :items-to-show="1"
  :autoplay="2000"
  :wrap-around="true"
  :pauseAutoplayOnHover="true"
  class="transition-carousel"
>
      <Slide v-for="(item, index) in testimonials" :key="index">
        <div class="bg-white p-6 rounded-lg shadow w-64 mx-auto">
          <img :src="item.photo" class="w-16 h-16 rounded-full mx-auto mb-4" />
          <h3 class="font-semibold">{{ item.name }}</h3>
          <p class="text-yellow-400 text-xl">★★★★★</p>
          <p class="mt-2 text-gray-700">"{{ item.comment }}"</p>
        </div>
      </Slide>
    </Carousel>
  </section>
</template>

<script>
import { Carousel, Slide } from 'vue3-carousel'
import 'vue3-carousel/dist/carousel.css'

export default {
  components: {
    Carousel,
    Slide
  },
  data() {
    return {
      testimonials: [
        {
          name: 'Budi Santoso',
          photo: '/src/assets/budi.jpg',
          comment: 'Suasananya nyaman banget, cocok buat kerja atau sekadar ngobrol santai.'
        },
        {
          name: 'Sari Ayu',
          photo: '/src/assets/sari.jpg',
          comment: 'Interiornya estetik, cocok buat foto-foto dan nongkrong bareng teman.'
        },
        {
          name: 'Joko Anwar',
          photo: '/src/assets/joko.jpg',
          comment: 'Harga terjangkau, rasa premium. Worth every sip!'
        }
      ]
    }
  }
}
</script>

<style scoped>
/* Smooth fade between slides */
.transition-carousel .carousel__slide {
  opacity: 0;
  transform: scale(0.98);
  transition: opacity 1s ease-in-out, transform 1s ease-in-out;
}

.transition-carousel .carousel__slide--visible {
  opacity: 1;
  transform: scale(1);
}
</style>
