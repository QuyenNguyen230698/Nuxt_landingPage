<template>
    <ClientOnly>
    <div>
        <slot />
        <ButtonScrollToTop />
    </div>
</ClientOnly>
</template>
<script setup>
import AOS from 'aos'
import 'aos/dist/aos.css'

// Reference to the target element
const targetElement = ref(null) 

onMounted(() => {
    AOS.init({
      offset: 200,
      duration: 600,
      easing: 'ease-in-sine',
      delay: 100,
      once: false,
      mirror: true,
      anchorPlacement: 'top-bottom',
    });
    window.addEventListener('scroll', refreshAOS);
})

onUnmounted(() => {
    window.removeEventListener('scroll', refreshAOS);
})

const refreshAOS = () => {
    if (targetElement.value && isElementInViewport(targetElement.value)) {
        AOS.refresh();
    }
}

</script>
<style>
    
</style>
