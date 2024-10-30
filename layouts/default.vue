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
const isScrolled = ref(false)
const targetElement = ref(null) 

onMounted(() => {
    window.addEventListener('scroll', checkScrollHover);
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
    window.removeEventListener('scroll', checkScrollHover);
    window.removeEventListener('scroll', refreshAOS);
})

const checkScrollHover = () => {
    if (window.scrollY > 50) {
        isScrolled.value = true;
    } else {
        isScrolled.value = false;
    }
}

const refreshAOS = () => {
    if (targetElement.value && isElementInViewport(targetElement.value)) {
        AOS.refresh();
    }
}

const scrollToForm = (formId) => {
  const element = document.getElementById(formId);
  if (element) {
    element.scrollIntoView({ 
      behavior: 'smooth',
      block: 'center'
    });
  }
}

// Helper function to check if an element is in the viewport
const isElementInViewport = (el) => {
    const rect = el.getBoundingClientRect();
    return (
        rect.top >= 0 &&
        rect.left >= 0 &&
        rect.bottom <= (window.innerHeight || document.documentElement.clientHeight) &&
        rect.right <= (window.innerWidth || document.documentElement.clientWidth)
    );
}
</script>
<style>
.nav-item {
  position: relative;
  color: #000000;
}

/* Sử dụng :hover trên .nav-item để kích hoạt hiệu ứng */
.nav-item:hover:after {
  width: 100%;
}

.nav-item:after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0; /* Bắt đầu từ 0, sẽ mở rộng khi hover */
  height: .125rem;
  background-color: rgba(34, 34, 34, 1);
  transition: width 0.5s cubic-bezier(.4, 0, .2, 1); /* Thêm hiệu ứng mở rộng */
}
    
</style>
