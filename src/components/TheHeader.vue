<script setup>
import { ref, onMounted } from "vue";

const menu = ref([
  {
    name: "Technology",
    url: "#technology",
  },
  {
    name: "Archivement",
    url: "#archivement",
  },
  {
    name: "Education",
    url: "#education",
  },
  {
    name: "Opensource",
    url: "#opensource",
  },
  {
    name: "Contact",
    url: "#contact",
  },
]);

const showNavigation = ref(false);

const handleScroll = () => {
  const scrollPosition = window.scrollY;
  if (scrollPosition > 100) {
    // Change the opacity to 100% when scrolled down 100px
    document.querySelector(".fixed-nav").classList.add("bg-opacity-70");
    document.querySelector(".text-color").classList.add("text-black");
  } else {
    // Change the opacity to 10% when not scrolled down enough
    document.querySelector(".fixed-nav").classList.remove("bg-opacity-70");
    document.querySelector(".text-color").classList.remove("text-black");
  }
};

onMounted(() => {
  // Listen to the scroll event
  window.addEventListener("scroll", handleScroll);
});
</script>

<template>
  <nav
    class="fixed-nav fixed w-full h-16 bg-white shadow-md bg-opacity-10"
    style="z-index: 999"
  >
    <div
      class="h-full max-w-6xl px-3 mx-auto flex items-center justify-between"
    >
      <!-- logo -->
      <div
        class="border rounded-full bg-white w-auto px-4 h-8 flex items-center justify-center"
      >
        <div class="flex items-center space-x-2">
          <h3 class="font-bold">YORN SREYMAO</h3>
          <p>👩‍💻</p>
        </div>
      </div>

      <!-- menu -->
      <!-- desktop menu  -->
      <div class="hidden md:flex text-color text-white items-center space-x-6">
        <a
          class="font-medium hover:text-yellow-500"
          v-for="(item, index) in menu"
          :key="index"
          :href="item.url"
        >
          {{ item.name }}
        </a>
      </div>

      <!-- mobile menu  -->
      <div class="flex md:hidden">
        <button @click="showNavigation = true">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="white"
            class="w-6 h-6"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
            />
          </svg>
        </button>
      </div>

      <!-- mobile menu list  -->
      <div
        v-if="showNavigation"
        class="fixed items-start p-4 space-y-6 bg-white flex flex-col w-3/4 transition h-screen shadow-lg left-0 top-0"
        @mouseleave="showNavigation = false"
      >
        <a
          class="font-medium hover:text-yellow-500"
          v-for="(item, index) in menu"
          :key="index"
          :href="item.url"
          @click="showNavigation = false"
        >
          {{ item.name }}
        </a>
      </div>
    </div>
  </nav>
</template>
