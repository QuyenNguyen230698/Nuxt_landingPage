<template>
    <div>
        <header class="bg-[#222] sticky z-30 top-0 left-0 right-0 shadow w-full">
            <div class="container mx-auto px-0 sm:px-6 lg:px-8 flex items-center justify-between h-8 sm:h-12 lg:h-16 xl:h-20 relative navbar">
                <div class="navbar-start h-16 min-h-16">
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
                                <summary class="flex items-center gap-2 cursor-pointer hover:bg-gray-700 px-2 rounded">
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
    </div>
</template>
<script>

</script>
<style>
    
</style>
