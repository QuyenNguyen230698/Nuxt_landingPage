<template>
    <ClientOnly>
    <div>
        <header class="bg-black hover:bg-white transition-colors duration-1000 ease-in-out sticky z-50 top-0 left-0 right-0 shadow w-full"
        :class="{'bg-white': isScrolled}">
            <div class="container mx-auto px-2 sm:px-4 lg:px-6 xl:px-8  flex items-center justify-between h-8 sm:h-12 lg:h-16 xl:h-20 relative navbar">
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
                            <button class="text-xs sm:text-sm md:text-base py-2 cursor-pointer">REGISTER PARTICIPATE</button>
                            <button class="text-xs sm:text-sm md:text-base py-2 cursor-pointer">REGISTER BOOTH</button>
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
        <footer class="relative z-10 bg-black w-full">
            <footer class="container px-6 lg:px-0 mx-auto text-white">
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8 py-8 md:py-12 lg:py-8">
                    <div class="flex flex-col items-center lg:items-start">
                        <img src="/public//image/logo/main.png" alt="" class="w-32 h-10 object-contain mb-4">
                        <nav class="flex space-x-4 mt-4">
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
                        <nav class="flex flex-col justify-start h-full">
                            <div class="cursor-pointer text-base mb-4">
                                <a href="#">About Us</a>
                            </div>
                        </nav>
                        <nav class="flex flex-col justify-start h-full">
                            <div class="cursor-pointer text-base mb-4">
                                <a href="#">News</a>
                            </div>
                        </nav>
                        <nav class="flex flex-col justify-start h-full">
                            <div class="cursor-pointer text-base mb-4">
                                <a href="#">Contact</a>
                            </div>
                        </nav>
                        <nav class="flex flex-col justify-start h-full">
                            <div>
                                <h3 class="text-base mb-4">Sustainability</h3>
                                <ul class="space-y-2">
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">Environment</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">Social</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">Governance</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">NetZero 2030</a>
                                    </li>
                                </ul>
                            </div>
                        </nav>
                        <nav class="flex flex-col justify-start h-full">
                            <div>
                                <h3 class="text-base mb-4">Solutions</h3>
                                <ul class="space-y-2">
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">Hospitality Furniture</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">Architecture & Construction</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">Modular Homes</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">Hospitality Management</a>
                                    </li>
                                </ul>
                            </div>
                        </nav>
                        <nav class="flex flex-col justify-start h-full">
                            <div>
                                <h3 class="text-base mb-4">Projects</h3>
                                <ul class="space-y-2">
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">Category</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">3D Tour</a>
                                    </li>
                                </ul>
                            </div>
                        </nav>
                        <nav class="flex flex-col justify-start h-full">
                            <div class="cursor-pointer text-base mb-4">
                                <a href="#">Careers</a>
                            </div>
                        </nav>
                        <nav class="flex flex-col justify-start h-full">
                            <div class="cursor-pointer text-base mb-4">
                                <a href="#">Contest</a>
                            </div>
                        </nav>
                        <nav class="flex flex-col justify-start h-full">
                            <div class="cursor-pointer text-base mb-4">
                                <a href="#">Brochure</a>
                            </div>
                        </nav>
                    </div>
                </div>
                <div class="py-2 text-white">
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
      once: false
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
    
</style>
