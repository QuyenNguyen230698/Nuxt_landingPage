<template>
    <!-- workshop & speaker -->
    <div class="relative w-full py-6">
          <div class="absolute inset-0 h-6 lg:h-8 w-2/3 lg:w-1/3 " style="top: 45%;">
            <img v-for="item in background" :src="item.image" :key="item.image" class="w-full h-full object-cover">
          </div>
          <div class="container mx-auto p-0 flex flex-col lg:flex-row w-full h-full gap-3 px-3 md:px-6 lg:px-0">
            <div class="w-full lg:w-1/3 flex flex-col items-start justify-center">
              <div data-aos="fade-up" data-aos-duration='1000' data-aos-offset=“100” class="flex lg:flex-col items-start justify-center gap-1 uppercase font-bold text-xl md:text-2xl lg:text-3xl text-black">
                <div class="w-fit bg-transparent title-body">{{ $t('app.event.hot1') }}</div>
                <div class="w-fit bg-transparent title-body">{{ $t('app.event.hot2') }}</div>
              </div>
            </div>
            <div class="w-full lg:w-2/3 grid grid-cols-2 lg:grid-cols-4 gap-1 py-3">
              <img 
                v-for="(item, index) in workshop" 
                :src="item.image" 
                :key="item.image" 
                data-aos="fade-up"
                :data-aos-duration="700 + (index * 100)"
                data-aos-offset="100"
                class="w-full h-auto bg-cover aspect-square"
              >
            </div>
          </div>
        </div>
</template>

<script setup>
const props = defineProps({
    workshop: {
        type: Array,
        default: () => []
    },
    background: {
        type: Array,
        default: () => []
    }
})
</script>

<style scoped>

</style>