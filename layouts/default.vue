<template>
    <div>
        <header class="bg-[#222] hover:bg-white transition-colors duration-1000 ease-in-out sticky z-50 top-0 left-0 right-0 shadow w-full"
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
                            <button class="text-xs sm:text-sm md:text-base py-2 cursor-pointer">REGISTER PARTICIPATE</button>
                            <button class="text-xs sm:text-sm md:text-base py-2 cursor-pointer">REGISTER BOOTH</button>
                            </div>
                        </div>
                        <div class="relative">
                            <details class="text-nowrap">
                                <summary class="flex items-center gap-2 cursor-pointer px-2 rounded">
                                    <img class="w-10 h-10" src="/public/image/netzero/header/language-en.png" alt="language" />
                                </summary>
                                <!-- Chỉ giữ lại một menu dropdown và thêm các tùy chọn ngôn ngữ vào -->
                                <div class="absolute right-0 mt-2 bg-white rounded-md shadow-lg overflow-hidden min-w-[160px]">
                                    <div class="flex items-center gap-2 px-3 py-2 hover:bg-gray-100 cursor-pointer">
                                        <img class="w-8 h-8" src="/public/image/netzero/header/language-en.png" alt="language" />
                                        <span>English</span>
                                    </div>
                                    <div class="flex items-center gap-2 px-3 py-2 hover:bg-gray-100 cursor-pointer">
                                        <img class="w-8 h-8" src="/public/image/netzero/header/language-vi.png" alt="language" />
                                        <span>Vietnamese</span>
                                    </div>
                                </div>
                            </details>
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
                            <details class="text-nowrap">
                                <summary class="flex items-center gap-2 cursor-pointer px-2 rounded">
                                    <img class="w-10 h-10" src="/public/image/netzero/header/language-en.png" alt="language" />
                                </summary>
                                <!-- Chỉ giữ lại một menu dropdown và thêm các tùy chọn ngôn ngữ vào -->
                                <div class="absolute right-0 mt-2 bg-white rounded-md shadow-lg overflow-hidden min-w-[160px]">
                                    <div class="flex items-center gap-2 px-3 py-2 hover:bg-gray-100 cursor-pointer">
                                        <img class="w-8 h-8" src="/public/image/netzero/header/language-en.png" alt="language" />
                                        <span>English</span>
                                    </div>
                                    <div class="flex items-center gap-2 px-3 py-2 hover:bg-gray-100 cursor-pointer">
                                        <img class="w-8 h-8" src="/public/image/netzero/header/language-vi.png" alt="language" />
                                        <span>Vietnamese</span>
                                    </div>
                                </div>
                            </details>
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
        <button style="z-index:999 !important;" class="fixed bottom-8 right-3 lg:right-8 bg-gray-800 text-white p-2 rounded-full shadow-lg hover:bg-gray-700 transition-colors duration-300 z-40 opacity-100"><svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 10l7-7m0 0l7 7m-7-7v18"></path></svg></button>
    </div>
</template>
<script>
export default {
  data() {
    return {
      isScrolled: false
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll() {
      this.isScrolled = window.scrollY > 50 // Kích hoạt khi scroll xuống 50px
    }
  }
}
</script>
<style>
    
</style>
