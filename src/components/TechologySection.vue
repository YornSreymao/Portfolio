<script setup>
import TitleSection from "./TitleSection.vue";
import { ref } from "vue";

const technologies = ref([
  "devicon-html5-plain",
  "devicon-css3-plain",
  "devicon-javascript-plain",
  "devicon-vuejs-plain-wordmark",
  "devicon-react-original-wordmark",
  "devicon-ruby-plain-wordmark colored",
  "devicon-typescript-plain",
  "devicon-nestjs-plain-wordmark colored",
  "devicon-postman-plain-workmark colored",
  "devicon-bootstrap-plain-wordmark",
  "devicon-vuetify-plain",
  "devicon-nodejs-plain-wordmark",
  "devicon-mongodb-plain-wordmark",
  "devicon-github-original",
  "devicon-gitlab-plain",
  "devicon-ubuntu-plain",
]);
</script>

<template>
  <TitleSection
    icon="/images/technology.png"
    title="Technology"
    description="Frameworks, Programming Languages, and tools I have experienced"
  />
  <div class="grid grid-cols-3 md:grid-cols-9 gap-6 mt-6 mb-20">
    <div
      v-for="(item, index) in technologies"
      :key="index"
      class="bg-white w-full h-full shadow-lg p-2 rounded-xl flex items-center justify-center hover:translate-y-[-5px] transition-transform"
    >
      <i class="colored" :class="item" style="font-size: 60px"></i>
    </div>
  </div>
</template>
