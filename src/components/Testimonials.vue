<script setup lang="ts">
const testimonials = [
  {
    id: 1,
    name: 'Silvia Lopes',
    image: '/images/clientes/silvia.jpeg',
    text: 'Adorei a qualidade das roupas! O atendimento foi excelente e a entrega super rápida.'
  },
  {
    id: 2,
    name: 'Camila Mendes',
    image: '/images/clientes/camila.jpeg',
    text: 'As peças são lindas e exclusivas. Sempre encontro algo especial para cada ocasião.'
  },
  {
    id: 3,
    name: 'Vitória Cristine',
    image: '/images/clientes/vitoria.jpeg',
    text: 'Melhor loja online! Os produtos são exatamente como nas fotos e chegam muito bem embalados.'
  }
];
</script>

<template>
  <section class="py-20 bg-secondary/30">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <h2 class="text-3xl md:text-4xl font-bold text-center mb-12">
        O que nossas clientes dizem
      </h2>
      
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <div v-for="testimonial in testimonials" 
             :key="testimonial.id"
             class="bg-white p-6 rounded-lg shadow-lg">
          <div class="flex items-center mb-4">
            <img :src="testimonial.image" 
                 :alt="testimonial.name"
                 class="w-12 h-12 rounded-full object-cover mr-4">
            <h3 class="font-medium">{{ testimonial.name }}</h3>
          </div>
          <p class="text-gray-600">{{ testimonial.text }}</p>
        </div>
      </div>
    </div>
  </section>
</template>