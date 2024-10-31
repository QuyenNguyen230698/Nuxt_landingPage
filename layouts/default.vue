<template>
  <ClientOnly>
    <div>
      <slot />
      <ButtonScrollToTop />
    </div>
  </ClientOnly>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
import AOS from "aos";
import "aos/dist/aos.css";

const showHeader = ref(false);
const scrollY = ref(0);
const updateScroll = () => {
  scrollY.value = window.scrollY;
  if (scrollY.value > 50) {
    showHeader.value = true;
  } else {
    showHeader.value = false;
  }
};

onMounted(() => {
  AOS.init({
    offset: 200,
    duration: 600,
    easing: "ease-in-sine",
    delay: 100,
    once: false,
    mirror: true,
    anchorPlacement: "top-bottom",
  });
  window.addEventListener("scroll", updateScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", updateScroll);
});
watch(scrollY, (newVal) => {
  if (newVal > 50) {
    showHeader.value = true;
  }
});

</script>
