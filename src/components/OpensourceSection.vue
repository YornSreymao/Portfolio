<script setup>
import TitleSection from "./TitleSection.vue";
import { ref } from "vue";

const opensources = ref([
  {
    name: "Buntith Portfolio",
    description: "Personal Website",
    url: "https://github.com/lengbuntith/buntith-portfolio",
  },
  {
    name: "Movieez",
    description: "Movie Streaming Website",
    url: "https://github.com/lengbuntith/project-movieez",
  },
  {
    name: "Travel Advisor",
    description: "Travel Advisor Website",
    url: "https://github.com/lengbuntith/Travel-Advisor",
  },
  {
    name: "Realtime Chat App",
    description: "Realtime Chat Application",
    url: "https://github.com/lengbuntith/Anakut-Chat-App-Website",
  },
]);
</script>

<template>
  <TitleSection
    icon="/images/technology.png"
    title="Open Source"
    description="Open Source Projects I have contributed to"
  />
  <div class="mt-6 mb-20">
    <div class="grid grid-cols-1 md:grid-cols-4 gap-10">
      <div
        v-for="(item, index) in opensources"
        :key="index"
        class="border rounded-lg bg-white shadow-lg"
      >
        <div class="p-5">
          <h5 class="text-lg font-bold">{{ item.name }}</h5>
          <p class="text-sm text-gray-500">{{ item.description }}</p>
        </div>
        <div class="flex justify-end p-5">
          <a
            :href="item.url"
            target="_blank"
            class="text-blue-500 hover:underline"
            >View</a
          >
        </div>
      </div>
    </div>
  </div>
</template>
