<script setup>
defineProps({
  icon: { type: String, required: true },
  title: { type: String, required: true },
  description: { type: String },
});
</script>

<template>
  <div class="flex items-center mb-3" :id="title.toLocaleLowerCase()">
    <img class="w-14 h-14 mr-2" :src="icon" :alt="title" />
    <div>
      <h3 class="text-2xl font-bold text-white capitalize">{{ title }}</h3>
      <p class="text-white font-light">
        {{ description }}
      </p>
    </div>
  </div>
</template>
