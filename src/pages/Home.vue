<template>
  <section class="min-h-screen flex flex-col justify-center items-center bg-[#F5F5F5] text-center px-6">
    <h1 class="font-display text-5xl md:text-6xl text-[#333] mb-6 animate-fadeInDown">Selamat Datang di Kedai Kami</h1>
    <p class="font-sans text-lg md:text-xl text-[#777] mb-8 animate-fadeIn">
      Nikmati pengalaman ngopi terbaik anda dengan suasana hangat sambil bersantai.
    </p>
    <a href="#menu" class="px-6 py-3 bg-[#C4A484] text-white rounded-full text-lg hover:bg-[#b58d6e] transition duration-300">
      Lihat Menu
    </a>
  </section>
</template>

<script setup>
// Tidak butuh script tambahan
</script>

<style scoped>
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(20px);}
  to { opacity: 1; transform: translateY(0);}
}
@keyframes fadeInDown {
  from { opacity: 0; transform: translateY(-20px);}
  to { opacity: 1; transform: translateY(0);}
}
.animate-fadeIn {
  animation: fadeIn 1s ease-out forwards;
}
.animate-fadeInDown {
  animation: fadeInDown 1s ease-out forwards;
}
</style>
