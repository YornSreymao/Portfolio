
<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Autoplay } from "swiper/modules";
import "swiper/css";
import { ref } from "vue";
import TitleSection from "./TitleSection.vue";

const modules = [Autoplay];

const archivements = ref([
  {
    image: "/images/VET.png",
    title: "VET AIR BUS EXPRESS",
    description:
      "we aim to be the No. 1 traveling choice for you in Cambodia and beyond.",
    link: "https://www.vetairbus.com/en/transit/resorts"
  },
  {
    image: "/images/cushy-store.png",
    title: "E-commerce Website for Curshy Store",
    description:
      "",
  },
  {
    image: "/images/tbmpharmacy.png",
    title: "E-commerce Website for TBM Pharmarcy",
    description:
      "",
  },
  {
    image: "/images/unicorntechnology.png",
    title: "Electronic Website for Unicorn Technology",
    description:
      "",
  },
  {
    image: "/images/phsarmall.png",
    title: "Multi-Vendor Shop Website",
    description:
      "",
  },
  {
    image: "/images/phsarworld.png",
    title: "Construction Website for Phsarworld",
    description:
      "",
  },
]);
</script>

<template>
  <TitleSection
    icon="/images/reward.png"
    title="archivement"
    description="Projects websites I have completed so far"
  />

  <div>
    <swiper
      class="mb-20"
      :slidesPerView="1"
      :spaceBetween="10"
      :pagination="{
        clickable: true,
      }"
      :autoplay="{
        delay: 2500,
        disableOnInteraction: false,
      }"
      :breakpoints="{
        '640': {
          slidesPerView: 1,
          spaceBetween: 20,
        },
        '768': {
          slidesPerView: 2,
          spaceBetween: 40,
        },
        '1024': {
          slidesPerView: 3,
          spaceBetween: 50,
        },
      }"
      :modules="modules"
    >
      <swiper-slide
        v-for="(item, i) in archivements"
        :key="i"
        class="shadow-lg border rounded-lg my-2 bg-white"
      >
        <div class="w-full p-4">
          <div class="h-40 overflow-hidden">
            <img
              class="w-full rounded-lg shadow"
              style="object-fit: contain"
              :src="item.image"
              :alt="item.title"
            />
          </div>
          <div class="mt-2 h-40">
            <h5 class="mb-2 text-lg line-clamp-2">{{ item.title }}</h5>
            <p class="text-sm text-gray-500 hover:text-gray-700 line-clamp-3">
              {{ item.description }} 
            </p>
            <a class="mt-2 text-blue-500 underline" :href="item.link" target="_blank">View</a>
          </div>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>
