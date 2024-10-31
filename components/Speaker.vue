<template>
    <!-- speaker -->
    <div class="relative w-full py-6">
          <div class="absolute lg:right-0 h-6 lg:h-8 w-2/3 lg:w-1/3 " style="top: 45%;">
            <img v-for="item in background" :src="item.image" :key="item.image" class="w-full h-full object-cover">
          </div>
          <div class="container mx-auto p-0 grid grid-cols-1 lg:grid-cols-3 w-full h-full gap-3 px-3 md:px-6 lg:px-0">
            <div class="order-2 lg:order-1 lg:col-span-2 w-full overflow-x-hidden overflow-y-hidden">
              <ImageGallary :imageUrls="speaker" :useActive="true" :duration="1000"/>
            </div>
            <div class="order-1 lg:order-2 lg:col-span-1 flex flex-col items-start lg:items-end justify-center">
              <div data-aos="fade-up" data-aos-duration='1000' data-aos-offset=“100” class="flex lg:flex-col items-end justify-center gap-1 uppercase font-bold text-xl md:text-2xl lg:text-3xl text-black">
                <div class="w-fit bg-transparent title-body">{{ $t('app.speaker.speaker1') }}</div>
                <div class="w-fit bg-transparent title-body">{{ $t('app.speaker.speaker2') }}</div>
              </div>
            </div>
          </div>
        </div>
</template>

<script setup>
const props = defineProps({
    speaker: {
        type: Array,
        default: () => []
    },
    background: {
        type: Array,
        default: () => []
    }
})
</script>

<style lang="scss" scoped>

</style>