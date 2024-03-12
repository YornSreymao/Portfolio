<script setup>
import TitleSection from "./TitleSection.vue";
import { ref } from "vue";

const educations = ref([
  {
    school_name: "Institute of Technology of Cambodia",
    school_logo: "/images/education/itc.png",
    from: "2018",
    to: "2023",
    description: "Bachelor of Engineering in Computer Science",
  },
  {
    school_name: "Sok An Soben High School",
    school_logo: "/images/education/High_school.jpg",
    from: "2012",
    to: "2018",
    description: "High School",
  },
]);
</script>

<template>
  <TitleSection
    icon="/images/graduation-cap.png"
    title="Education"
    description="My education background "
  />
  <ul class="flex flex-col space-y-10 mt-6 mb-20">
    <li
      v-for="(item, index) in educations"
      :key="index"
      class="flex space-x-4 md:space-x-10"
      :class="index < educations.length - 1 ? 'border-b pb-10' : 'pb-0'"
    >
      <div class="w-32 h-32">
        <img
          class="w-full rounded-full"
          style="object-fit: cover"
          :src="item.school_logo"
          alt=""
        />
      </div>
      <div class="space-y-2">
        <h5 class="text-lg text-white font-bold">{{ item.school_name }}</h5>
        <p class="text-white">{{ item.description }}</p>
        <div class="flex text-white space-x-3">
          <h6>{{ item.from }}</h6>
          <span>-</span>
          <h6>{{ item.to }}</h6>
        </div>
      </div>
    </li>
  </ul>
</template>
