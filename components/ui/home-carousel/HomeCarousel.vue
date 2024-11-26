<script setup>
import "vue3-carousel/dist/carousel.css";
import { ref } from "vue";

const currentSlide = ref(0);

const galleryConfig = {
  itemsToShow: 1,
  wrapAround: true,
  autoplay: false,
  pauseAutoplayOnHover: true,
};

const images = Array.from({ length: 2 }, (_, index) => ({
  id: index + 1,
  url: `/images/san_francesco/${index + 1}.jpg`,
}));
</script>

<template>
  <Carousel
    id="gallery"
    v-bind="galleryConfig"
    v-model="currentSlide"
    class="rounded-lg shadow-lg overflow-hidden w-full"
  >
    <Slide v-for="image in images" :key="image.id">
      <div class="carousel__item w-full">
        <img
          :src="image.url"
          alt="Gallery Image"
          class="gallery-image w-full h-auto object-cover"
        />
      </div>
    </Slide>

    <template #addons>
      <Navigation />
    </template>
  </Carousel>
</template>

<style scoped>
.gallery-image {
  width: 100%;
  object-fit: cover;
}
</style>
