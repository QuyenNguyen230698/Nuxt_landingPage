<template>
    <div class="flex flex-col w-full h-full mt-2 mb-4">
          <div data-aos="fade-up" data-aos-duration='1000' data-aos-offset=“100” class="text-center uppercase font-bold text-xl md:text-2xl lg:text-3xl text-black bg-white py-6">
            <h2 class="title-body">{{ $t('app.media.communication') }}</h2>
          </div>
          <div class="flex w-full flex-col container mx-auto px-12">
            <ImageGallary :imageUrls="media" :useActive="false" :duration="1000" useGap="gap-6"/>
          </div>
         </div>
</template>

<script setup>
const props = defineProps({
    media: {
        type: Array,
        default: () => []
    }
})
</script>

<style scoped>

</style>