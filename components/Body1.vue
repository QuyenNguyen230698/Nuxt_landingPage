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
          <div class="absolute inset-0 h-6 lg:h-8 w-2/3 lg:w-1/3 top-[45%]">
            <img v-for="item in background" :src="item.image" :key="item.image" class="w-full h-full object-cover">
          </div>
          <div class="container mx-auto p-0 flex flex-col lg:flex-row w-full h-full gap-3 px-3 md:px-6 lg:px-0">
            <div class="w-full lg:w-1/3 flex flex-col items-start justify-center">
              <div class="flex lg:flex-col items-start justify-center gap-1 font-bold">
                <div class="w-fit bg-transparent title-body">EVENTS</div>
                <div class="w-fit bg-transparent title-body">FEATURED</div>
              </div>
            </div>
            <div class="w-full lg:w-2/3 grid grid-cols-2 lg:grid-cols-4 gap-1 py-3">
              <img v-for="item in workshop" :src="item.image" :key="item.image" class="w-full h-auto bg-cover aspect-square">
            </div>
          </div>
        </div>
        <div class="relative w-full py-6">
          <div class="absolute lg:right-0 h-6 lg:h-8 w-2/3 lg:w-1/3 top-[45%]">
            <img v-for="item in background" :src="item.image" :key="item.image" class="w-full h-full object-cover">
          </div>
          <div class="container mx-auto p-0 grid grid-cols-1 lg:grid-cols-3 w-full h-full gap-3 px-3 md:px-6 lg:px-0">
            <div class="order-2 lg:order-1 lg:col-span-2 w-full overflow-x-hidden overflow-y-hidden">
              <div class="w-full grid grid-cols-2 lg:grid-cols-4 gap-1 py-3">
                <img v-for="item in speaker" :src="item.image" :key="item.image" class="w-full h-full object-cover">
              </div>
            </div>
            <div class="order-1 lg:order-2 lg:col-span-1 flex flex-col items-start lg:items-end justify-center">
              <div class="flex lg:flex-col items-end justify-center gap-1 font-bold">
                <div class="w-fit bg-transparent title-body">GUEST</div>
                <div class="w-fit bg-transparent title-body">SPEAKERS</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- Time line -->
    <div class="flex flex-col w-full h-full">
      <div class="relative text-start uppercase font-bold text-xl md:text-2xl lg:text-3xl text-black bg-white py-6">
        <div class="absolute inset-0 right-0 h-8 w-1/3 top-[45%]">
          <img v-for="item in background" :src="item.image" :key="item.image" class="w-full h-full object-center">
        </div>
        <h2 class="container mx-auto title-body">TIME LINE</h2>
      </div>
      <div class="w-full h-full container mx-auto grid grid-cols-2 gap-1 px-4 md:px-16 lg:px-28">
        <img v-for="item in timeLine" :src="item.image" :key="item.image" class="w-full h-auto">
      </div>
    </div>
    <!-- Register -->
     <div>Register</div>
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
];
const workshop = [
  {image:'/image/netzero/workshop/vi-VN/workshop-1.webp'},
  {image:'/image/netzero/workshop/vi-VN/workshop-2.webp'},
  {image:'/image/netzero/workshop/vi-VN/workshop-3.webp'},
  {image:'/image/netzero/workshop/vi-VN/workshop-4.webp'},
];
const speaker = [
  {image:'/image/netzero/speaker/vi-VN/speaker-1.webp'},
  {image:'/image/netzero/speaker/vi-VN/speaker-1.webp'},
  {image:'/image/netzero/speaker/vi-VN/speaker-1.webp'},
  {image:'/image/netzero/speaker/vi-VN/speaker-1.webp'},
];
const timeLine = [
  {image:'/image/netzero/timeline/vi-VN/timeline-one.webp'},
  {image:'/image/netzero/timeline/vi-VN/timeline-3.webp'},
  {image:'/image/netzero/timeline/vi-VN/timeline-2.webp'},
  {image:'/image/netzero/timeline/vi-VN/timeline-4.webp'},
];

</script>
<style scoped>
.bg-main{
  background-image: url('/public/image/netzero/background/bg-main.jpg');
  background-size: cover;
  background-position: center;
};
.title-body {
  color: #000000;
  text-transform: uppercase;
  --tw-text-opacity: 1;
  font-weight: bold;
  font-size: 2.25rem;
  line-height: 2.5rem;
}
</style>
