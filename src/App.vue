<script setup>
import TheHeader from "./components/TheHeader.vue";
import HeroSection from "./components/HeroSection.vue";
import TechologySection from "./components/TechologySection.vue";
import EducationSection from "./components/EducationSection.vue";
import ArchivementSection from "./components/ArchivementSection.vue";
import OpensourceSection from "./components/OpensourceSection.vue";
import ContactSection from "./components/ContactSection.vue";
import { onMounted } from "vue";

onMounted(() => {
  // Get all anchor links and attach a click event listener
  document.querySelectorAll('a[href^="#"]').forEach((anchor) => {
    anchor.addEventListener("click", function (e) {
      e.preventDefault();

      const targetId = this.getAttribute("href");
      const targetElement = document.querySelector(targetId);

      // Scroll smoothly to the target element
      targetElement.scrollIntoView({
        behavior: "smooth",
      });
    });
  });
});
</script>

<template>
  <TheHeader />
  <HeroSection />
  <main class="max-w-6xl mx-auto px-3 py-10">
    <TechologySection />
    <ArchivementSection />
    <EducationSection />
    <OpensourceSection />
    <ContactSection />
  </main>
</template>

<style></style>
