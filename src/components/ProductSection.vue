<script setup lang="ts">
import Carousel from '../components/Carousel.vue';

const categories = [
  {
    id: 1,
    name: 'Roupas',
    image: [
      '/images/roupas/01.jpeg',
      '/images/roupas/02.jpeg',
      '/images/roupas/03.jpeg',
      '/images/roupas/04.jpeg',
      '/images/roupas/05.jpeg',
    ],
    href: '#roupas',
    description: "descrição"
  },
  {
    id: 2,
    name: 'Bolsas',
    image: ['/images/bolsas/01.jpeg'],
    href: '#bolsas',
    description: "descrição"
  },
  {
    id: 3,
    name: 'Sandálias',
    image: [
      '/images/sandalias/01.jpeg',
      '/images/sandalias/02.jpeg',
      '/images/sandalias/03.jpeg',
      '/images/sandalias/04.jpeg',
    ],
    href: '#sandalias',
    description: "descrição"
  },
  {
    id: 4,
    name: 'Cosméticos',
    image: [
      '/images/cosmeticos/01.jpeg',
      '/images/cosmeticos/02.jpeg',
      '/images/cosmeticos/03.jpeg',
      '/images/cosmeticos/04.jpeg',
      '/images/cosmeticos/05.jpeg',
      '/images/cosmeticos/06.jpeg',
      '/images/cosmeticos/07.jpeg',
    ] ,
    href: '#cosmeticos',
    description: "descrição"
  },
  {
    id: 4,
    name: 'T-Shirts',
    image: [
      '/images/roupas/01.jpeg',
      '/images/roupas/02.jpeg',
    ] ,
    href: '#t-shirts',
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