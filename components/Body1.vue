<template>
  <div class="relative w-full z-20 overflow-hidden flex flex-col">
    <img src="/public/image/netzero/header/banner.jpg" alt="" />
    <div class="bg-main w-full h-full relative flex flex-col">
      <div class="w-full h-full">
        <!-- header & section -->
        <div class="flex flex-col w-full container mx-auto">
          <div class="flex items-center justify-center py-6">
            <img
            class="w-auto h-8 sm:h-10 lg:h-16 object-fit"
            src="/public/image/netzero/header/next-1.png"
            alt="body 1"
          />
          <div class="h-6 sm:h-8 bg-black mx-2 lg:mx-8" style="width: 1px;"></div>
          <img
            class="w-auto h-8 sm:h-10 lg:h-16 object-fit"
            src="/public/image/netzero/header/next-2.png"
            alt="body 2"
          />
          </div>
          <div class="grid grid-cols-1 md:grid-cols-2 items-center justify-center w-full h-full px-2 md:px-16 lg:px-24">
            <img v-for="item in section" :src="item.image" :key="item.image" class="w-full h-auto object-fit">
          </div>
        </div>
        <!-- workshop & speaker -->
        <div class="relative w-full py-6">
          <div class="absolute inset-0 h-6 lg:h-8 w-2/3 lg:w-1/3 position-left-right">
            <img v-for="item in background" :src="item.image" :key="item.image">
          </div>
          <div class="container"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const section = [
  {image:'/image/netzero/section/vi-VN/1.webp'},
  {image:'/image/netzero/section/vi-VN/2fix.webp'},
  {image:'/image/netzero/section/vi-VN/3.webp'},
  {image:'/image/netzero/section/vi-VN/4.webp'},
];
const background = [
  {image:'/image/netzero/background/bg-title.png'}
]

</script>
<style scoped>
.bg-main{
  background-image: url('/public/image/netzero/background/bg-main.jpg');
  background-size: cover;
  background-position: center;
};
.position-left-right {
  top: 45%;
}
</style>
