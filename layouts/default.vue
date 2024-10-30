<template>
    <ClientOnly>
    <div>
        <header class="bg-black hover:bg-white transition-colors duration-1000 ease-in-out sticky z-50 top-0 left-0 right-0 shadow w-full"
        :class="{'bg-white': isScrolled}">
            <div class="container mx-auto px-2 sm:px-4 lg:px-6 xl:px-8 animate-fade-down duration-1000 ease-in-out flex items-center justify-between h-8 sm:h-12 lg:h-16 xl:h-20 relative navbar">
                <div class="navbar-start h-8 sm:h-12 lg:h-16 xl:h-20">
                    <a href="#">
                        <img class="w-fit h-auto object-contain max-w-full max-h-full" src="/public/image/netzero/header/logo.png" alt="logo" />
                    </a>
                </div>
                <div class="navbar-end h-10 flex justify-end">
                    <div class="flex">
                        <div class="flex flex-col w-full h-full gap-6">
                            <div class="container mx-auto flex gap-6 text-white">
                            <button class="text-xs sm:text-sm md:text-base py-2 cursor-pointer">{{ $t('app.form.signEvent') }}</button>
                            <button class="text-xs sm:text-sm md:text-base py-2 cursor-pointer">{{ $t('app.form.signBooth') }}</button>
                            </div>
                        </div>
                        <div class="relative">
                            <LanguageSwitch/>
                        </div>
                    </div>
                </div>
            </div>
            <!-- hover header -->
            <div class="container mx-auto px-2 sm:px-4 lg:px-6 xl:px-8 flex items-center justify-between h-8 sm:h-12 lg:h-16 xl:h-20 absolute top-0 left-0 right-0 navbar opacity-0 hover:opacity-100 hover:z-50"
            :class="{'opacity-100': isScrolled}">
                <div class="navbar-start h-8 sm:h-12 lg:h-16 xl:h-20">
                    <a href="#">
                        <img class="w-fit h-auto object-contain max-w-full max-h-full" src="/public/image/netzero/header/logo-light.png" alt="logo" />
                    </a>
                </div>
                <div class="navbar-end h-10 flex justify-end">
                    <div class="flex">
                        <div class="flex flex-col w-full h-full gap-6">
                            <div class="container mx-auto flex gap-6">
                            <button @click="scrollToForm('form1')" class="nav-item text-xs sm:text-sm md:text-base py-2 cursor-pointer">{{ $t('app.form.signEvent') }}</button>
                            <button @click="scrollToForm('form1')" class="nav-item text-xs sm:text-sm md:text-base py-2 cursor-pointer">{{ $t('app.form.signBooth') }}</button>
                            </div>
                        </div>
                        <div class="relative">
                            <LanguageSwitch/>
                        </div>
                    </div>
                </div>
            </div>
        </header>
        <div>
            <slot />
        </div>
        <footer class="relative z-10 bg-black w-full overflow-hidden">
            <footer class="container px-6 lg:px-0 mx-auto text-white">
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8 py-8 md:py-12 lg:py-8">
                    <div class="flex flex-col items-center lg:items-start">
                        <img data-aos="fade-up" data-aos-duration="800" data-aos-offset=“100” src="/public//image/logo/main.png" alt="" class="w-32 h-10 object-contain mb-4">
                        <nav data-aos="fade-up" data-aos-duration="1000" data-aos-offset=“100” class="flex space-x-4 mt-4">
                            <a href="#">
                                <i class="bi bi-facebook text-xl"></i>
                            </a>
                            <a href="#">
                                <i class="bi bi-youtube text-xl"></i>
                            </a>
                            <a href="#">
                                <i class="bi bi-instagram text-xl"></i>
                            </a>
                            <a href="#">
                                <i class="bi bi-linkedin text-xl"></i>
                            </a>
                        </nav>
                    </div>
                    <div class="lg:col-span-3 grid grid-cols-2 lg:grid-cols-3 gap-8 lg:items-start">
                        <nav data-aos="fade-up" data-aos-duration="800" data-aos-offset=“100” class="flex flex-col justify-start h-full">
                            <div class="cursor-pointer text-base mb-4">
                                <a href="#">{{ $t('footer.aboutUs') }}</a>
                            </div>
                        </nav>
                        <nav data-aos="fade-up" data-aos-duration="800" data-aos-offset=“100” class="flex flex-col justify-start h-full">
                            <div class="cursor-pointer text-base mb-4">
                                <a href="#">{{ $t('footer.news') }}</a>
                            </div>
                        </nav>
                        <nav data-aos="fade-up" data-aos-duration="800" data-aos-offset=“100” class="flex flex-col justify-start h-full">
                            <div class="cursor-pointer text-base mb-4">
                                <a href="#">{{ $t('footer.contact') }}</a>
                            </div>
                        </nav>
                        <nav data-aos="fade-up" data-aos-duration="900" data-aos-offset=“100” class="flex flex-col justify-start h-full">
                            <div>
                                <h3 class="text-base mb-4">{{ $t('footer.sustainability') }}</h3>
                                <ul class="space-y-2">
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">{{ $t('footer.environment') }}</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">{{ $t('footer.social') }}</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">{{ $t('footer.governance') }}</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">{{ $t('footer.netZero2030') }}</a>
                                    </li>
                                </ul>
                            </div>
                        </nav>
                        <nav data-aos="fade-up" data-aos-duration="900" data-aos-offset=“100” class="flex flex-col justify-start h-full">
                            <div>
                                <h3 class="text-base mb-4">{{ $t('footer.solutions') }}</h3>
                                <ul class="space-y-2">
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">{{ $t('footer.hospitalityFurniture') }}</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">{{ $t('footer.architectureAndConstruction') }}</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">{{ $t('footer.modularHomes') }}</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">{{ $t('footer.hospitalityManagement') }}</a>
                                    </li>
                                </ul>
                            </div>
                        </nav>
                        <nav data-aos="fade-up" data-aos-duration="900" data-aos-offset=“100” class="flex flex-col justify-start h-full">
                            <div>
                                <h3 class="text-base mb-4">{{ $t('footer.projects') }}</h3>
                                <ul class="space-y-2">
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">{{ $t('footer.category') }}</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">{{ $t('footer.threeDTour') }}</a>
                                    </li>
                                </ul>
                            </div>
                        </nav>
                        <nav data-aos="fade-up" data-aos-duration="1000" data-aos-offset=“100” class="flex flex-col justify-start h-full">
                            <div class="cursor-pointer text-base mb-4">
                                <a href="#">{{ $t('footer.career') }}</a>
                            </div>
                        </nav>
                        <nav data-aos="fade-up" data-aos-duration="1000" data-aos-offset=“100” class="flex flex-col justify-start h-full">
                            <div class="cursor-pointer text-base mb-4">
                                <a href="#">{{ $t('footer.contest') }}</a>
                            </div>
                        </nav>
                        <nav data-aos="fade-up" data-aos-duration="1000" data-aos-offset=“100”  class="flex flex-col justify-start h-full">
                            <div class="cursor-pointer text-base mb-4">
                                <a href="#">{{ $t('footer.brochure') }}</a>
                            </div>
                        </nav>
                    </div>
                </div>
                <div class="py-2 text-gray-500">
                    <div class="flex flex-col lg:flex-row items-center justify-between text-sm test-gray-400">
                        <p>© 2024 TranDuc Corporation</p>
                    </div>
                </div>
            </footer>
        </footer>
        <ButtonScrollToTop />
    </div>
</ClientOnly>
</template>
<script setup>
import AOS from 'aos'
import 'aos/dist/aos.css'

const isScrolled = ref(false)
const targetElement = ref(null) // Reference to the target element

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
