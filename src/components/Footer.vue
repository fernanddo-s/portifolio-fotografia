<template>
  <footer class="bg-gray-900 text-white py-12">
    <div class="container mx-auto px-4">
      <div class="grid md:grid-cols-2 gap-8 mb-8">
        <div>
          <h3 class="text-xl font-bold mb-4">Gerardo Produções & Eventos</h3>
          <p class="text-gray-400">
            Capturando momentos especiais e transformando-os em memórias eternas.
          </p>
        </div>
        
        <div>
          <h3 class="text-xl font-bold mb-4">Links Rápidos</h3>
          <ul class="space-y-2">
            <li><a href="#home" class="text-gray-400 hover:text-white">Home</a></li>
            <li><a href="#portfolio" class="text-gray-400 hover:text-white">Portfólio</a></li>
            <li><a href="#about" class="text-gray-400 hover:text-white">Sobre Nós</a></li>
            <li><a href="#contact" class="text-gray-400 hover:text-white">Contato</a></li>
          </ul>
        </div>
      </div>
      
      <div class="border-t border-gray-800 pt-8 text-center text-gray-400">
        <p>&copy; {{ new Date().getFullYear() }} Gerardo Produções & Eventos. Todos os direitos reservados.</p>
      </div>
    </div>
  </footer>
</template>