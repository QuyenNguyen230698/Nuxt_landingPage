<template>
    <!-- Sponsorship -->
    <div class="flex flex-col w-full h-full mt-2 mb-4">
        <div data-aos="fade-up" data-aos-duration='1000' data-aos-offset=“100” class="text-center uppercase font-bold text-xl md:text-2xl lg:text-3xl text-black bg-white py-6">
          <h2 class="title-body">{{ $t('app.media.ponsorship') }}</h2>
        </div>
        <div class="w-full container mx-auto px-4">
          <div class="flex flex-nowrap justify-center items-center gap-6 overflow-x-hidden">
            <div data-aos="fade-up" data-aos-duration='1000' data-aos-offset=“100” class="flex-shrink-0 flex-grow-0 w-1/4 lg:w-1/6 flex justify-center">
              <img :src="sponsorship[0].image" :key="sponsorship[0].image" class="w-full h-auto max-h-16 min-h-16 object-contain">
            </div>
            <div data-aos="fade-up" data-aos-duration='1100' data-aos-offset=“100” class="flex-shrink-0 flex-grow-0 w-1/4 lg:w-1/6 flex justify-center">
              <img :src="sponsorship[1].image" :key="sponsorship[1].image" class="w-full h-auto max-h-16 min-h-16 object-contain">
            </div>
            <div data-aos="fade-up" data-aos-duration='1200' data-aos-offset=“100” class="flex-shrink-0 flex-grow-0 w-1/4 lg:w-1/6 flex justify-center">
              <img :src="sponsorship[2].image" :key="sponsorship[2].image" class="w-full h-auto max-h-16 min-h-16 object-contain">
            </div>
          </div>
        </div>
       </div>
</template>

<script setup>
const props = defineProps({
    sponsorship: {
        type: Array,
        default: () => []
    }
})

</script>

<style scoped>

</style>