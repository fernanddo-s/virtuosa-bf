<template>
  <div class="carousel">
    <div
      class="carousel-wrapper"
      :style="{ transform: `translateX(-${currentIndex * 100}%)` }"
    >
      <div
        class="carousel-item"
        v-for="(image, index) in images"
        :key="index"
      >
        <img :src="image" :alt="'Imagem ' + (index + 1)" />
      </div>
    </div>

    <button class="prev" @click="prevSlide">❮</button>
    <button class="next" @click="nextSlide">❯</button>

    <div class="indicators">
      <span
        v-for="(_, index) in images"
        :key="index"
        :class="{ active: index === currentIndex }"
        @click="goToSlide(index)"
      ></span>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

interface Props {
  images: string[];
}

const props = defineProps<Props>();

const currentIndex = ref<number>(0);

const nextSlide = (): void => {
  currentIndex.value = (currentIndex.value + 1) % props.images.length;
};

const prevSlide = (): void => {
  currentIndex.value =
    (currentIndex.value - 1 + props.images.length) % props.images.length;
};

const goToSlide = (index: number): void => {
  currentIndex.value = index;
};
</script>

<style scoped>
.carousel {
  position: relative;
  max-width: 600px;
  margin: auto;
  overflow: hidden;
}
.carousel-wrapper {
  display: flex;
  transition: transform 0.5s ease-in-out;
}
.carousel-item {
  flex: 0 0 100%;
}
img {
  width: 100%;
  height: 300px;
  object-fit: cover;
  display: block;
}
button {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(0, 0, 0, 0.5);
  color: white;
  border: none;
  cursor: pointer;
  padding: 10px;
  z-index: 10;
}
button.prev {
  left: 10px;
}
button.next {
  right: 10px;
}
.indicators {
  display: flex;
  justify-content: center;
  gap: 10px;
  margin-top: 10px;
}
.indicators span {
  width: 10px;
  height: 10px;
  background: gray;
  border-radius: 50%;
  cursor: pointer;
}
.indicators span.active {
  background: black;
}
</style>
