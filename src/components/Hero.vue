<script setup lang="ts">
</script>

<template>
  <section class="relative h-screen flex items-center justify-center bg-secondary/30 mt-16 teste">
    <div class="absolute inset-0 teste">
      <img src="/images/image.png"
           class="w-full h-full object-cover opacity-90 image-cover"
           alt="Hero background">
    </div>
  </section>
</template>

<style >
/* Ajustes adicionais para dispositivos pequenos */
@media (max-width: 768px) {
  .image-cover {
    object-fit: contain;
    height: auto;
  }

  .teste{
    height: 20vh;
  }
}
</style>