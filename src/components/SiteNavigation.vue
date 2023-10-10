<template>
  <header class="sticky top-0 bg-wheather-primary shadow-lg">
    <nav class="container flex flex-col sm:flex-row items-center gap-4 text-white py-6">
      <RouterLink :to="{ name: 'home' }">
        <div class="flex item-center gap-3">
          <i class="fa-solid fa-sun text-2xl"></i>
          <p class="text-2xl">The local wheather</p>
        </div>
      </RouterLink>
      <div class="flex gap-3 flex-1 justify-end align-center">
        <i
          @click="toggleModal"
          class="fa-solid fa-info fa-circle-info text-xl hover:text-weather-secondary duration-150 cursor-pointer"
        ></i>
        <i
          class="fa-solid fa-plus text-xl hover:text-weather-secondary duration-150 cursor-pointer"
        ></i>
      </div>
      <BaseModel :modalActive="modalActive" @close-modal="toggleModal">
        <h1 class="text-black">Hello from model</h1></BaseModel
      >
    </nav>
  </header>
</template>

<script setup>
import { ref } from "vue";
import { RouterLink } from "vue-router";
import BaseModel from "./BaseModel.vue";
const modalActive = ref(null);
const toggleModal = () => {
  modalActive.value = !modalActive.value;
};
</script>
