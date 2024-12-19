<script setup lang="ts">
import { ref } from 'vue';

const isMenuOpen = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};
</script>

<template>
  <header class="fixed w-full bg-white/95 shadow-md z-50">
    <nav class="container mx-auto px-4 py-4">
      <div class="flex justify-between items-center">
        <a href="#" class="text-2xl font-bold text-gray-800">Gerardo Produções & Eventos</a>
        
        <!-- Mobile menu button -->
        <button @click="toggleMenu" class="md:hidden">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path strokeLinecap="round" strokeLinejoin="round" strokeWidth="2" 
                  d="M4 6h16M4 12h16M4 18h16" />
          </svg>
        </button>

        <!-- Desktop menu -->
        <div class="hidden md:flex items-center space-x-8">
          <a href="#home" class="text-gray-600 hover:text-gray-900">Home</a>
          <a href="#portfolio" class="text-gray-600 hover:text-gray-900">Portfólio</a>
          <a href="#about" class="text-gray-600 hover:text-gray-900">Sobre Nós</a>
          <a href="#contact" class="text-gray-600 hover:text-gray-900">Contato</a>
          <button class="bg-blue-600 text-white px-6 py-2 rounded-full hover:bg-blue-700 
                         transition duration-300">
            Solicitar Orçamento
          </button>
        </div>
      </div>

      <!-- Mobile menu -->
      <div v-show="isMenuOpen" class="md:hidden">
        <div class="flex flex-col space-y-4 mt-4 pb-4">
          <a href="#home" class="text-gray-600 hover:text-gray-900">Home</a>
          <a href="#portfolio" class="text-gray-600 hover:text-gray-900">Portfólio</a>
          <a href="#about" class="text-gray-600 hover:text-gray-900">Sobre Nós</a>
          <a href="#contact" class="text-gray-600 hover:text-gray-900">Contato</a>
          <button class="bg-blue-600 text-white px-6 py-2 rounded-full hover:bg-blue-700 
                         transition duration-300">
            Solicitar Orçamento
          </button>
        </div>
      </div>
    </nav>
  </header>
</template>