<script setup>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue";
// Import Swiper styles
import "swiper/css";
</script>

<template>
  <swiper :slides-per-view="1" class="mb-10 bg-black">
    <swiper-slide style="height: 600px !important">
      <div
        class="grid grid-cols-1 md:grid-cols-2 max-w-6xl mx-auto px-3 h-full"
      >
        <div class="h-full flex flex-col justify-center mx-auto md:block">
          <h1 class="text-white text-4xl font-bold md:mt-40 shadow">
            YORN SREYMAO
          </h1>
          <h2 class="text-3xl font-bold mt-4 text-purple-500">
            WEB DEVELOPER
          </h2>
          <p class="text-white text-2xl font-bold mt-6">
            I am an experienced web development. I have completed numerous projects using new technologies.
          </p>
          <p class="text-white mt-6">
            "I'm just a developer who enjoys studying new technologies."
          </p>
        </div>
        <div class="hidden md:flex items-center justify-center">
          <img
            class="w-full"
            style="object-fit: contain; height: 390px"
            src="/images/hero/MAO.png"
          />
        </div>
      </div>
    </swiper-slide>
  </swiper>
</template>
