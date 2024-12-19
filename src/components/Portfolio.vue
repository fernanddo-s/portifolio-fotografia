<script setup lang="ts">
import { ref, computed } from 'vue';

interface Image {
  id: number;
  src: string;
  alt: string;
  category: string;
}

const images = ref<Image[]>([
  {
    id: 1,
    src: 'https://placecats.com/millie_neo/300/200',
    alt: 'Casamento elegante ao ar livre',
    category: 'Casamentos'
  },
  {
    id: 2,
    src: 'https://placecats.com/neo_2/300/200',
    alt: 'Cerimônia de formatura',
    category: 'Formaturas'
  },
  {
    id: 3,
    src: 'https://placecats.com/bella/300/200',
    alt: 'Festa de 15 anos',
    category: 'Festas de 15 Anos'
  },
]);

const selectedCategory = ref('Todos');
const categories = ['Todos', 'Casamentos', 'Formaturas', 'Festas de 15 Anos'];

const filteredImages = computed(() => {
  if (selectedCategory.value === 'Todos') return images.value;
  return images.value.filter(img => img.category === selectedCategory.value);
});
</script>

<template>
  <section id="portfolio" class="py-20 bg-gray-50">
    <div class="container mx-auto px-4">
      <h2 class="text-4xl font-bold text-center mb-12">Nosso Portfólio</h2>
      
      <div class="flex justify-center space-x-4 mb-8">
        <button v-for="category in categories" 
                :key="category"
                @click="selectedCategory = category"
                :class="[
                  'px-4 py-2 rounded-full',
                  selectedCategory === category 
                    ? 'bg-blue-600 text-white' 
                    : 'bg-white text-gray-600 hover:bg-gray-100'
                ]">
          {{ category }}
        </button>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="image in filteredImages" 
             :key="image.id" 
             class="group relative overflow-hidden rounded-lg shadow-lg">
          <img :src="image.src" 
               :alt="image.alt"
               class="w-full h-64 object-cover transform transition duration-300 
                      group-hover:scale-110" />
          <div class="absolute inset-0 bg-black/50 opacity-0 group-hover:opacity-100 
                      transition duration-300 flex items-center justify-center">
            <p class="text-white text-lg font-semibold">{{ image.alt }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>