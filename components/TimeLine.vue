<template>
      <!-- Time line -->
      <div class="flex flex-col w-full h-full">
      <div class="relative text-start uppercase font-bold text-xl md:text-2xl lg:text-3xl text-black bg-white py-6">
        <div class="absolute inset-0 right-0 h-8 w-1/3 " style="top: 45%;">
          <img v-for="item in background" :src="item.image" :key="item.image" class="w-full h-full object-center">
        </div>
        <h2 data-aos="fade-down" data-aos-duration='500' data-aos-offset=“100” class="container mx-auto title-body">{{ $t('app.time.timeline') }}</h2>
      </div>
      <div class="w-full h-full container mx-auto grid grid-cols-1 md:grid-cols-2 gap-1 px-4 md:px-16 lg:px-28">
        <img 
          v-for="(item, index) in timeLine" 
          :src="item.image" 
          :key="item.image" 
          :data-aos="index % 2 === 0 ? 'fade-right' : 'fade-left'"
          :data-aos-duration="index < 2 ? 1000 : 1200"
          data-aos-offset="100"
          :class="[
            'w-full h-auto',
            // Thêm order cho mobile
            {'md:order-none': true},
            {'-order-1': index % 2 === 0},
            {'order-1': index % 2 !== 0}
          ]"
        >
      </div>
    </div>
</template>

<script setup>
const props = defineProps({
    timeLine: {
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