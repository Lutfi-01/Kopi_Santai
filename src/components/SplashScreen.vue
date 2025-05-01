<template>
  <div class="flex flex-col items-center justify-center h-screen bg-[#F5F5F5] transition-colors">
    <!-- SVG Kopi -->
    <div class="w-48 h-48 relative">
      <svg viewBox="0 0 200 200" class="w-full h-full">
        <!-- Gelas Kopi -->
        <rect x="50" y="80" width="100" height="100" rx="15" ry="15" fill="#6b4f3b" />
        
        <!-- Asap -->
        <g>
          <path d="M100 80 C90 70, 110 50, 100 40" stroke="#ccc" stroke-width="3" fill="none">
            <animateTransform 
              attributeName="transform" 
              type="translate" 
              from="0,0" 
              to="0,-20" 
              dur="2s" 
              repeatCount="indefinite" />
            <animate 
              attributeName="opacity" 
              values="1;0" 
              dur="2s" 
              repeatCount="indefinite" />
          </path>
          <path d="M120 80 C110 70, 130 50, 120 40" stroke="#ccc" stroke-width="3" fill="none">
            <animateTransform 
              attributeName="transform" 
              type="translate" 
              from="0,0" 
              to="0,-25" 
              dur="2.5s" 
              repeatCount="indefinite" />
            <animate 
              attributeName="opacity" 
              values="1;0" 
              dur="2.5s" 
              repeatCount="indefinite" />
          </path>
        </g>
      </svg>
    </div>

    <h1 class="text-5xl font-bold font-display mb-2 animate-bounce">K☕️pi Santai!</h1>
      <p class="text-lg font-light mb-6 animate-pulse">Sedang memuat kenikmatan...</p>

    <!-- Progress Bar -->
      <div class="w-64 bg-gray-300 rounded-full h-3 overflow-hidden">
        <div class="bg-[#C4A484] h-3 rounded-full transition-all duration-300" :style="{ width: progress + '%' }"></div>
      </div>
  </div>
</template>

<script setup>
  import { ref, onMounted } from 'vue'
  
  const isLoaded = ref(false)
  const progress = ref(0)
  
  onMounted(() => {
    const interval = setInterval(() => {
      if (progress.value < 100) {
        progress.value += 2
      } else {
        clearInterval(interval)
        setTimeout(() => {
          isLoaded.value = true
        }, 500) // Sedikit delay setelah 100%
      }
    }, 50) // Cepat lambat loading
  })
  </script>
