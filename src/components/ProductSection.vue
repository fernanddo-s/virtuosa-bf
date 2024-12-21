<script setup lang="ts">
import Carousel from '../components/Carousel.vue';

const categories = [
  {
    id: 1,
    name: 'Roupas',
    image: ['https://images.unsplash.com/photo-1434389677669-e08b4cac3105?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1005&q=80',
      'https://images.unsplash.com/photo-1543163521-1bf539c55dd2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1160&q=80',
    'https://images.unsplash.com/photo-1596462502278-27bfdc403348?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1160&q=80'
    ],
    href: '#roupas',
    description: "descrição"
  },
  {
    id: 2,
    name: 'Bolsas',
    image: ['https://images.unsplash.com/photo-1594633313593-bab3825d0caf?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1074&q=80'],
    href: '#bolsas',
    description: "descrição"
  },
  {
    id: 3,
    name: 'Sandálias',
    image: ['https://images.unsplash.com/photo-1543163521-1bf539c55dd2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1160&q=80',
    'https://images.unsplash.com/photo-1596462502278-27bfdc403348?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1160&q=80'
    ],
    href: '#sandalias',
    description: "descrição"
  },
  {
    id: 4,
    name: 'Cosméticos',
    image: ['https://images.unsplash.com/photo-1596462502278-27bfdc403348?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1160&q=80',
      'https://images.unsplash.com/photo-1543163521-1bf539c55dd2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1160&q=80',
    'https://images.unsplash.com/photo-1596462502278-27bfdc403348?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1160&q=80'
    ] ,
    href: '#cosmeticos',
    description: "descrição"
  }
];
</script>

<template>
  <section id="produtos" class="py-20 bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <h2 class="text-3xl md:text-4xl font-bold text-center mb-12">
        Nossas Categorias
      </h2>

      <div class="categorie-list">
        <div v-for="categorie in categories" :key="categorie.id" class="categorie-card">
          <Carousel :images="categorie.image"></Carousel>
          <h3 class="categorie-title">{{ categorie.name }}</h3>
          <!-- <p class="categorie-description">{{ categorie.description }}</p> -->
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.categorie-list {
  margin: 20px 0 20px 0;
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}
.categorie-card {
  width: 500px;
  border: 1px solid #ddd;
  border-radius: 8px;
  overflow: hidden;
  background: #fff;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}
.categorie-image {
  width: 100%;
  height: 300px;
  object-fit: cover;
}
.categorie-title {
  margin: 10px;
  font-size: 1.5rem;
  color: #333;
}
.categorie-description {
  margin: 10px;
  font-size: 1rem;
  color: #666;
}
</style>