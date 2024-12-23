<script setup lang="ts">
import { ref } from 'vue';
import { Bars3Icon, XMarkIcon } from '@heroicons/vue/24/outline';

const navigation = [
  { name: 'Roupas', href: '#roupas' },
  { name: 'Bolsas', href: '#bolsas' },
  { name: 'Sandálias', href: '#sandalias' },
  { name: 'Cosméticos', href: '#cosmeticos' },
  { name: 'T-Shirts', href: '#t-shirts' },
];

const isOpen = ref(false);
</script>

<template>
  <header class="bg-white shadow-sm fixed w-full top-0 z-50">
    <nav class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8" aria-label="Top">
      <div class="flex h-16 items-center justify-between">
        <div class="flex items-center">
          <a href="#" class="font-playfair text-2xl font-bold text-gray-900">
            Virtuosa
          </a>
        </div>
        
        <!-- Desktop Navigation -->
        <div class="hidden md:flex space-x-8">
          <a v-for="item in navigation" 
             :key="item.name" 
             :href="item.href"
             class="text-gray-700 hover:text-accent transition-colors duration-200 font-medium">
            {{ item.name }}
          </a>
        </div>

        <!-- Mobile menu button -->
        <div class="md:hidden">
          <button @click="isOpen = !isOpen" 
                  class="text-gray-700 hover:text-accent">
            <span class="sr-only">Open menu</span>
            <Bars3Icon v-if="!isOpen" class="h-6 w-6" />
            <XMarkIcon v-else class="h-6 w-6" />
          </button>
        </div>
      </div>

      <!-- Mobile Navigation -->
      <div v-show="isOpen" 
           class="md:hidden">
        <div class="space-y-1 pb-3 pt-2">
          <a v-for="item in navigation" 
             :key="item.name" 
             :href="item.href"
             class="block px-3 py-2 text-gray-700 hover:bg-accent/10 hover:text-accent"
             @click="isOpen = false">
            {{ item.name }}
          </a>
        </div>
      </div>
    </nav>
  </header>
</template>