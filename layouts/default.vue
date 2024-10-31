<template>
  <ClientOnly>
    <div>
      <slot />
      <ButtonScrollToTop />
    </div>
  </ClientOnly>
</template>

<script setup>
import AOS from "aos";
import "aos/dist/aos.css";

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
});

onUnmounted(() => {
});

</script>
