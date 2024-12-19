<script setup lang="ts">
import { ref } from 'vue';

const formData = ref({
  name: '',
  email: '',
  phone: '',
  eventType: '',
  message: ''
});

const eventTypes = [
  'Casamento',
  'Formatura',
  'Festa de 15 Anos',
  'Evento Corporativo',
  'Outro'
];

const submitForm = () => {
  console.log('Form submitted:', formData.value);
  // Add form submission logic here
};
</script>

<template>
  <section id="contact" class="py-20 bg-gray-50">
    <div class="container mx-auto px-4">
      <h2 class="text-4xl font-bold text-center mb-12">Entre em Contato</h2>
      
      <div class="grid md:grid-cols-2 gap-12">
        <div>
          <form @submit.prevent="submitForm" class="space-y-6">
            <div>
              <label class="block text-gray-700 mb-2">Nome</label>
              <input v-model="formData.name"
                     type="text"
                     required
                     class="w-full px-4 py-2 rounded-lg border focus:ring-2 focus:ring-blue-500" />
            </div>
            
            <div>
              <label class="block text-gray-700 mb-2">Email</label>
              <input v-model="formData.email"
                     type="email"
                     required
                     class="w-full px-4 py-2 rounded-lg border focus:ring-2 focus:ring-blue-500" />
            </div>
            
            <div>
              <label class="block text-gray-700 mb-2">Telefone</label>
              <input v-model="formData.phone"
                     type="tel"
                     required
                     class="w-full px-4 py-2 rounded-lg border focus:ring-2 focus:ring-blue-500" />
            </div>
            
            <div>
              <label class="block text-gray-700 mb-2">Tipo de Evento</label>
              <select v-model="formData.eventType"
                      required
                      class="w-full px-4 py-2 rounded-lg border focus:ring-2 focus:ring-blue-500">
                <option value="">Selecione o tipo de evento</option>
                <option v-for="type in eventTypes" 
                        :key="type" 
                        :value="type">
                  {{ type }}
                </option>
              </select>
            </div>
            
            <div>
              <label class="block text-gray-700 mb-2">Mensagem</label>
              <textarea v-model="formData.message"
                        rows="4"
                        required
                        class="w-full px-4 py-2 rounded-lg border focus:ring-2 focus:ring-blue-500">
              </textarea>
            </div>
            
            <button type="submit"
                    class="w-full bg-blue-600 text-white py-3 rounded-lg hover:bg-blue-700 
                           transition duration-300">
              Enviar Mensagem
            </button>
          </form>
        </div>
        
        <div class="space-y-8">
          <div>
            <h3 class="text-xl font-bold mb-4">Informações de Contato</h3>
            <div class="space-y-4">
              <p class="flex items-center">
                <span class="mr-2">📍</span>
                Rua Horacio Oliveira, 415 - Lagoa do Carneiro
              </p>
              <p class="flex items-center">
                <span class="mr-2">📱</span>
                (88) 99962-0346
              </p>
              <p class="flex items-center">
                <span class="mr-2">📧</span>
                gerardoproducoeseeventos@gmail.com
              </p>
            </div>
          </div>
          
          <div>
            <h3 class="text-xl font-bold mb-4">Redes Sociais</h3>
            <div class="flex space-x-4">
              <a href="#" class="text-gray-600 hover:text-blue-600">Instagram</a>
              <a href="#" class="text-gray-600 hover:text-blue-600">Facebook</a>
              <a href="#" class="text-gray-600 hover:text-blue-600">LinkedIn</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>