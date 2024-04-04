<template>
  <header class="sticky top-0 bg-black shadow-lg">
    <nav class="container flex flex-col sm:flex-row items-center text-white gap-4 py-6">
      <RouterLink :to="{ name: 'home' }">
        <div class="flex items-center gap-3">
          <i class="fa-solid fa-sun text-2xl"></i>
          <p class="text-2xl">The Weather App</p>
        </div>
      </RouterLink>

      <div class="flex gap-3 flex-1 justify-end">
        <i
          class="fa-solid fa-circle-up text-xl hover:text-weather-secondary duration-150 cursor-pointer"
          @click="toggleModal"
        ></i>
        <i
          class="fa-solid fa-plus text-xl hover:text-weather-secondary duration-150 cursor-pointer"
        ></i>
      </div>

      <BaseModel :modalActive="modalActive" @close-modal="toggleModal">
        <div class="text-black">
          <h1 class="text-2xl mb-1">About</h1>
          <p>This is Popup</p>
        </div>
      </BaseModel>
    </nav>
  </header>
</template>

<script setup>
import { ref } from "vue";
import { RouterLink } from "vue-router";
import BaseModel from "../components/BaseModel.vue";

const modalActive = ref(null);
const toggleModal = () => {
  modalActive.value = !modalActive.value;
};
</script>
