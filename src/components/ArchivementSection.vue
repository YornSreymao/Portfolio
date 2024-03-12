
<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Autoplay } from "swiper/modules";
import "swiper/css";
import { ref } from "vue";
import TitleSection from "./TitleSection.vue";

const modules = [Autoplay];

const archivements = ref([
  {
    image: "/images/emenu-mobile.png",
    title: "E-menu website for 20 restuarants, Coffee...",
    description:
      "A digital menu for modern restuarant \n A digital menu for modern restuarant \n A digital menu for modern restuarant",
    link: "https://www.vetairbus.com/en/transit/resorts"
  },
  {
    image: "/images/cushy-store.png",
    title: "E-commerce Website for Curshy Store",
    description:
      "A online Website easy to find products and buy study material, book, kids products etc.",
  },
  {
    image: "/images/tbmpharmacy.png",
    title: "E-commerce Website for TBM Pharmarcy",
    description:
      "A online Website easy to find hundreds of medicine products and buy any time",
  },
  {
    image: "/images/unicorntechnology.png",
    title: "Electronic Website for Unicorn Technology",
    description:
      "A online Website easy to find accessories, gaming laptop, desktop etc in Unicorn Technology Store",
  },
  {
    image: "/images/phsarmall.png",
    title: "Multi-Vendor Shop Website",
    description:
      "Phsarmall is a center place for many shop can sell their products on website and easy for customer to find and buy many type of products in one place.",
  },
  {
    image: "/images/phsarworld.png",
    title: "Construction Website for Phsarworld",
    description:
      "A online Website selling contruction material products and booking sevice in construction fields",
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
