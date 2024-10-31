<template>
     <!-- section -->
    <div class="flex flex-col w-full container mx-auto">
          <div class="flex items-center justify-center py-6">
            <img data-aos="fade-right" data-aos-duration='1000' data-aos-offset=“100”
            class="w-auto h-8 sm:h-10 lg:h-16 object-fit"
            src="/public/image/netzero/header/next-1.png"
            alt="body 1"
          />
          <div data-aos="fade-up" data-aos-duration='1200' data-aos-offset=“100” class="h-6 sm:h-8 bg-black mx-2 lg:mx-8" style="width: 1px;"></div>
          <img data-aos="fade-left" data-aos-duration='1000' data-aos-offset=“100”
            class="w-auto h-8 sm:h-10 lg:h-16 object-fit"
            src="/public/image/netzero/header/next-2.png"
            alt="body 2"
          />
          </div>
          <div class="grid grid-cols-1 md:grid-cols-2 items-center justify-center w-full h-full px-2 md:px-16 lg:px-24">
            <img 
              v-for="(item, index) in section" 
              :src="item.image" 
              :key="item.image" 
              :data-aos="index % 2 === 0 ? 'fade-right' : 'fade-left'"
              :data-aos-duration="index < 2 ? 900 : 1000"
              data-aos-offset=“100”
              class="w-full h-auto object-fit"
            />
          </div>
        </div>
</template>

<script setup>
const props = defineProps({
    section: {
        type: Array,
        default: () => []
    }
})

</script>

<style scoped>

</style>