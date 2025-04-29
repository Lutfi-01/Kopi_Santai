<template>
  <section id="menu" class="py-16 bg-white px-6">
    <div class="max-w-6xl mx-auto text-center">
      <h2 class="font-display text-4xl text-[#333] mb-12">Menu</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-10">
        <div v-for="item in menuItems" :key="item.name" class="p-6 border rounded-2xl shadow-md hover:shadow-xl transition">
          <h3 class="text-2xl font-bold mb-2">{{ item.name }}</h3>
          <p class="text-[#777] mb-4">{{ item.description }}</p>
          <span class="text-[#C4A484] font-semibold text-lg">{{ item.price }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const menuItems = [
  { name: 'Espresso', description: 'Kopi hitam pekat dengan aroma kuat.', price: 'Rp25.000' },
  { name: 'Latte', description: 'Perpaduan espresso dan susu lembut.', price: 'Rp30.000' },
  { name: 'Cappuccino', description: 'Espresso dengan foam susu tebal.', price: 'Rp30.000' },
  { name: 'Americano', description: 'Espresso dicampur air panas.', price: 'Rp22.000' },
  { name: 'Mocha', description: 'Coklat panas dengan espresso.', price: 'Rp35.000' },
  { name: 'Flat White', description: 'Espresso dengan susu creamy.', price: 'Rp32.000' },
]
</script>
