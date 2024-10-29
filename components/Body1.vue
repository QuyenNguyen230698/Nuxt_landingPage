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
     <div class="relative w-full h-full flex flex-col py-6">
      <div class="container mx-auto flex gap-6">
        <button class="text-xs sm:text-sm md:text-base nav-item py-2 cursor-pointer">REGISTER PARTICIPATE</button>
        <button class="text-xs sm:text-sm md:text-base nav-item py-2 cursor-pointer">REGISTER BOOTH</button>
      </div>
     </div>
     <div class="flex flex-col w-full h-full bg-black">
      <!-- form 1 -->
      <section class="container mx-auto flex flex-col overflow-hidden items-center bg-black">
        <div class="relative hero-module">
          <div class="relative grid-module">
            <div class="wrapper-container">
              <div class="grid lg:grid-cols-2 md:grid-cols-2 gap-5 py-8">
                <!-- image -->
                <div class="lg:col-span-1 col-auto md:order-2 order-2 text-center">
                  <img src="/public/image/netzero/form/image.jpg" class="w-full h-auto object-contain aspect-square">
                </div>
                <div class="lg:col-span-1 col-auto flex flex-col lg:items-start items-center justify-start md:order-1 order-1 text-right w-full">
                  <section class="w-full text-white bg-black">
                    <div class="flex flex-col gap-6 w-full">
                      <div class="grid grid-cols-1 gap-5 md:grid-cols-2 md:gap-4 w-full">
                        <div class="col-span-2">
                          <label class="block mb-1 font-light text-base">
                            <span class="text-base flex items-center text-center">
                              Full name
                            </span>
                          </label>
                          <input type="text" placeholder="Your full name" class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base">
                        </div>
                        <div class="col-span-2">
                          <label>
                            <span class="text-base flex items-center text-center">Participation date</span>
                          </label>
                          <div class="grid grid-cols-2">
                            <div class="col-span-1">
                              <label class="flex items-start">
                                <input type="checkbox" checked class="text-sm border border-white rounded-full">
                                <p class="ml-3">21/11/2024</p>
                              </label>
                            </div>
                            <div class="col-span-1">
                              <label class="flex items-start">
                                <input type="checkbox" checked class="text-sm border border-white rounded-full">
                                <p class="ml-3">21/11/2024</p>
                              </label>
                            </div>
                          </div>
                        </div>
                        <div class="col-span-2 lg:col-span-1">
                          <label class="block mb-1 font-light text-base">
                            <span class="text-base flex items-center text-center">
                              Email
                            </span>
                          </label>
                          <input type="email" placeholder="Your email" class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base">
                        </div>
                        <div class="col-span-2 lg:col-span-1">
                          <label class="block mb-1 font-light text-base">
                            <span class="text-base text-center flex items-center">Phone number</span>
                          </label>
                          <input type="tel" placeholder="Your phone number" class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base">
                        </div>
                        <div class="col-span-2">
                          <label class="flex items-center">
                            <input type="checkbox" class="text-sm border border-white rounded-full">
                            <p class="ml-3">Are you a student?</p>
                          </label>
                        </div>
                        <div class="col-span-2">
                          <label class="block mb-1 font-light text-base">
                            <span class="text-base flex items-center text-center">Company name</span>
                          </label>
                          <input type="text" placeholder="Your company name" class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base">
                        </div>
                        <div class="col-span-2">
                          <label class="block mb-1 font-light text-base">
                            <span class="text-base flex items-center text-center">Position</span>
                          </label>
                          <input type="text" placeholder="Position" class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base">
                        </div>
                        <div class="col-span-2">
                          <label class="inline-flex items-center">
                            <span class="text-sm text-gray-400 text-justify">
                              We are committed to using customer information safely, legally, and in compliance with current laws and regulations.
                            </span>
                          </label>
                        </div>
                        <div class="col-span-2 flex justify-center">
                          <button class="w-full btn bg-white rounded-none text-black py-1 md:py-2 hover:bg-gray-600 hover:text-white transition-colors duration-300 ease-in-out">Register</button>
                        </div>
                      </div>
                    </div>
                  </section>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
      <!-- form 2 -->
      <section class="container mx-auto flex flex-col overflow-hidden items-center bg-black">
        <div class="relative hero-module">
          <div class="relative grid-module">
            <div class="wrapper-container">
              <div class="grid lg:grid-cols-2 md:grid-cols-2 gap-5 py-8">
                <!-- image -->
                <div class="lg:col-span-1 col-auto md:order-1 order-1 text-center">
                  <img src="/public/image/netzero/form/booth.jpg" class="w-full h-auto object-contain aspect-square">
                </div>
                <div class="lg:col-span-1 col-auto flex flex-col lg:items-start items-center justify-start md:order-2 order-2 text-right w-full">
                  <section class="w-full text-white bg-black">
                    <div class="flex flex-col gap-6 w-full">
                      <div class="grid grid-cols-1 gap-5 md:grid-cols-2 md:gap-4 w-full">
                        <div class="col-span-2">
                          <label class="block mb-1 font-light text-base">
                            <span class="text-base flex items-center text-center">
                              Full name
                            </span>
                          </label>
                          <input type="text" placeholder="Your full name" class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base">
                        </div>
                        <div class="col-span-2">
                          <label class="block mb-1 font-light text-base">
                            <span class="text-base flex items-center text-center">
                              Email
                            </span>
                          </label>
                          <input type="email" placeholder="Your email" class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base">
                        </div>
                        <div class="col-span-2">
                          <label class="block mb-1 font-light text-base">
                            <span class="text-base text-center flex items-center">Phone number</span>
                          </label>
                          <input type="tel" placeholder="Your phone number" class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base">
                        </div>
                        <div class="col-span-2">
                          <label class="flex items-center">
                            <input type="checkbox" class="text-sm border border-white rounded-full">
                            <p class="ml-3">Are you a student?</p>
                          </label>
                        </div>
                        <div class="col-span-2">
                          <label class="block mb-1 font-light text-base">
                            <span class="text-base flex items-center text-center">Company name</span>
                          </label>
                          <input type="text" placeholder="Your company name" class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base">
                        </div>
                        <div class="col-span-2">
                          <label class="block mb-1 font-light text-base">
                            <span class="text-base flex items-center text-center">Position</span>
                          </label>
                          <input type="text" placeholder="Position" class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base">
                        </div>
                        <div class="col-span-2">
                          <label class="inline-flex items-center">
                            <span class="text-sm text-gray-400 text-justify">
                              We are committed to using customer information safely, legally, and in compliance with current laws and regulations.
                            </span>
                          </label>
                        </div>
                        <div class="col-span-2 flex justify-center">
                          <button class="w-full btn bg-white rounded-none text-black py-1 md:py-2 hover:bg-gray-600 hover:text-white transition-colors duration-300 ease-in-out">Register</button>
                        </div>
                      </div>
                    </div>
                  </section>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
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
const register = [
  {image:'/image/netzero/form/image.jpg'},
  {image:'/image/netzero/form/booth.jpg'},
]

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
};
.btn {
  height: 2.5rem;
  min-height: 2.5rem;
}
.nav-item:after {
    bottom: 0;
    content: "";
    height: .125rem;
    left: 0;
    position: absolute;
    width: 0;
    --tw-bg-opacity: 1;
    background-color: rgb(34 34 34 / var(--tw-bg-opacity));
    transition-duration: .5s;
    transition-property: all;
    transition-timing-function: cubic-bezier(.4,0,.2,1);
};
.nav-item:hover:after,
.nav-item:active:after {
  width: 100%;
};
</style>
