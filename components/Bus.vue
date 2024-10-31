<template>
    <!-- Bus -->
    <div class="flex flex-col w-full h-full mt-2 mb-4">
          <div class="text-center uppercase font-bold text-xl md:text-2xl lg:text-3xl text-black bg-white py-6">
            <h2 data-aos="fade-up" data-aos-duration='1000' data-aos-offset=“100” class="title-body">{{ $t('app.bus.schedule') }}</h2>
          </div>
          <div class="flex flex-col lg:flex-row w-full px-12 lg:px-24 bg-black">
            <div data-aos="fade-right" data-aos-duration='1000' data-aos-offset=“100” class="w-full lg:w-1/2 aspect-[16/9] overflow-hidden">
              <img :src="bus[0].image" :key="bus[0].image" class="w-full h-full object-center">
            </div>
            <div data-aos="fade-left" data-aos-duration='1000' data-aos-offset=“100” class="w-full lg:w-1/2 aspect-[16/9] overflow-hidden">
              <img :src="bus[1].image" :key="bus[1].image" class="w-full h-full object-center">
            </div>
          </div>
         </div>
</template>

<script setup>
const props = defineProps({
    bus: {
        type: Array,
        default: () => []
    }
})

</script>

<style scoped>

</style>