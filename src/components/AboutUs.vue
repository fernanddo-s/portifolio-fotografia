<script setup lang="ts">
const team = [
  {
    name: 'Gerardo Oliveira',
    role: 'CEO',
    image: 'https://placecats.com/bella/300/200'
  },
  {
    name: 'Carlos',
    role: 'Fotógrafo',
    image: 'https://placecats.com/bella/300/200'
  },
  {
    name: 'Junior',
    role: 'Fotógrafo e Editor de Imagens',
    image: 'https://placecats.com/bella/300/200'
  }
];
</script>

<template>
  <section id="about" class="py-20">
    <div class="container mx-auto px-4">
      <h2 class="text-4xl font-bold text-center mb-12">Sobre Nós</h2>
      
      <div class="grid md:grid-cols-2 gap-12 items-center mb-16">
        <div>
          <h3 class="text-2xl font-bold mb-4">Nossa História</h3>
          <p class="text-gray-600 mb-4">
            Com experiência de mercado, temos o privilégio de capturar os momentos mais especiais 
            na vida de nossos clientes. Nossa paixão pela fotografia nos permite transformar 
            memórias em arte.
          </p>
          <p class="text-gray-600">
            Com uma equipe experiente e dedicada, garantimos que cada evento seja documentado 
            com profissionalismo, criatividade e atenção aos detalhes.
          </p>
        </div>
        <div class="relative">
          <img src="https://placecats.com/300/200" 
               alt="Nosso estúdio"
               class="rounded-lg shadow-lg" />
        </div>
      </div>

      <h3 class="text-2xl font-bold text-center mb-8">Nossa Equipe</h3>
      <div class="grid md:grid-cols-3 gap-8">
        <div v-for="member in team" 
             :key="member.name"
             class="text-center">
          <img :src="member.image" 
               :alt="member.name"
               class="w-48 h-48 rounded-full mx-auto mb-4 object-cover" />
          <h4 class="text-xl font-semibold">{{ member.name }}</h4>
          <p class="text-gray-600">{{ member.role }}</p>
        </div>
      </div>
    </div>
  </section>
</template>