<template>
    <div>
        <header class="bg-black hover:bg-white fixed top-0 left-0 right-0 z-50">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8 flex justify-between h-8 sm:h-12 lg:h-16 xl:h-20">
                <img src="/public/image/netzero/header/logo.png" alt="logo" />
                <div class="flex items-center">
                    <img class="w-8 h-8" src="/public/image/netzero/header/language-en.png" alt="language" />
                </div>
            </div>
            <div class="container mx-auto px-4 sm:px-6 lg:px-8 flex justify-between absolute top-0 left-0 right-0 h-full opacity-0 hover:opacity-100 transition-opacity duration-500">
                <img src="/image/netzero/header/logo-light.png" alt="Logo Light" />
                <div class="flex items-center">
                    <img class="w-8 h-8" src="/public/image/netzero/header/language-vi.png" alt="language" />
                </div>
            </div>
        </header>
        <div class="mt-8 sm:mt-12 lg:mt-16 xl:mt-20">
            <img src="/public/image/netzero/header/banner.jpg" alt="logo" />
        </div>
        <div>
            <slot />
        </div>
    </div>
</template>
<script>

</script>
<style>
    
</style>
