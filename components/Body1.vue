<template>
  <div class="relative w-full z-20 overflow-hidden flex flex-col">
    <img data-aos="fade-up" data-aos-duration='1000' src="/public/image/netzero/header/banner.jpg" alt="" />
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
              <!-- <div class="w-full grid grid-cols-2 lg:grid-cols-4 gap-1 py-3">
                <img v-for="item in speaker" :src="item.image" :key="item.image" class="w-full h-full object-cover">
              </div> -->
              <ImageGallary :imageUrls="speaker" :useActive="true" :duration="500"/>
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
        <button @click="showForm = 'participate'" :class="{'active': showForm === 'participate'}" class="text-xs sm:text-sm md:text-base nav-item py-2 cursor-pointer">REGISTER PARTICIPATE</button>
        <button @click="showForm = 'booth'" :class="{'active': showForm === 'booth'}" class="text-xs sm:text-sm md:text-base nav-item py-2 cursor-pointer">REGISTER BOOTH</button>
      </div>
     </div>
     <div class="flex flex-col w-full h-full bg-black">
      <!-- form 1 -->
      <section v-if="showForm === 'participate'" class="container mx-auto flex flex-col overflow-hidden items-center bg-black">
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
      <section v-if="showForm === 'booth'" class="container mx-auto flex flex-col overflow-hidden items-center bg-black">
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
     <!-- partner -->
      <div class="w-full h-full flex flex-col mt-2 mb-4">
        <div class="text-center uppercase font-bold text-xl md:text-2xl lg:text-3xl text-black bg-white py-6">
          <h2 class="title-body">PARTNER</h2>
        </div>
        <div class="container w-full mx-auto px-4">
          <div class="grid grid-cols-2 lg:grid-cols-4 gap-6 overflow-x-hidden">
            <div class="flex justify-center">
              <img src="" class="w-full h-auto max-h-16 min-h-16 object-contain bg-black">
            </div>
            <div class="flex justify-center">
              <img src="" class="w-full h-auto max-h-16 min-h-16 object-contain bg-black">
            </div>
            <div class="flex justify-center">
              <img src="" class="w-full h-auto max-h-16 min-h-16 object-contain bg-black">
            </div>
            <div class="flex justify-center">
              <img src="" class="w-full h-auto max-h-16 min-h-16 object-contain bg-black">
            </div>
          </div>
        </div>
      </div>
      <!-- Media sponsorship -->
       <div class="flex flex-col w-full h-full mt-2 mb-4">
        <div class="text-center uppercase font-bold text-xl md:text-2xl lg:text-3xl text-black bg-white py-6">
          <h2 class="title-body">MEDIA SPONSORSHIP</h2>
        </div>
        <div class="w-full container mx-auto px-4">
          <div class="flex flex-nowrap justify-center items-center gap-6 overflow-x-hidden">
            <div class="flex-shrink-0 flex-grow-0 w-1/4 lg:w-1/6 flex justify-center">
              <img :src="sponsorship[0].image" :key="sponsorship[0].image" class="w-full h-auto max-h-16 min-h-16 object-contain">
            </div>
            <div class="flex-shrink-0 flex-grow-0 w-1/4 lg:w-1/6 flex justify-center">
              <img :src="sponsorship[1].image" :key="sponsorship[1].image" class="w-full h-auto max-h-16 min-h-16 object-contain">
            </div>
            <div class="flex-shrink-0 flex-grow-0 w-1/4 lg:w-1/6 flex justify-center">
              <img :src="sponsorship[2].image" :key="sponsorship[2].image" class="w-full h-auto max-h-16 min-h-16 object-contain">
            </div>
          </div>
        </div>
       </div>
       <!-- Media -->
        <div class="flex flex-col w-full h-full mt-2 mb-4">
          <div class="text-center uppercase font-bold text-xl md:text-2xl lg:text-3xl text-black bg-white py-6">
            <h2 class="title-body">MEDIA</h2>
          </div>
          <div class="flex w-full flex-col container mx-auto px-12">
            <ImageGallary :imageUrls="media" :useActive="false" :duration="500" useGap="gap-6"/>
          </div>
        </div>
        <!-- Bus -->
         <div class="flex flex-col w-full h-full mt-2 mb-4">
          <div class="text-center uppercase font-bold text-xl md:text-2xl lg:text-3xl text-black bg-white py-6">
            <h2 class="title-body">BUS SCHEDULE</h2>
          </div>
          <div class="flex flex-col lg:flex-row w-full px-12 lg:px-24 bg-black">
            <div class="w-full lg:w-1/2 aspect-[16/9] overflow-hidden">
              <img :src="bus[0].image" :key="bus[0].image" class="w-full h-full object-center">
            </div>
            <div class="w-full lg:w-1/2 aspect-[16/9] overflow-hidden">
              <img :src="bus[1].image" :key="bus[1].image" class="w-full h-full object-center">
            </div>
          </div>
         </div>
         <!-- Event Venue -->
          <div class="container mx-auto flex flex-col w-full h-full gap-6 mb-24">
            <div class="text-start uppercase font-bold text-xl md:text-2xl lg:text-3xl text-black bg-white py-6">
              <h2 class="title-body">EVENT VENUE</h2>
            </div>
            <div class="flex w-full min-h-96 bg-black"></div>
          </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const { locale } = useI18n()
const showForm = ref('participate')

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
  {src:'/image/netzero/speaker/vi-VN/speaker-1.webp'},
  {src:'/image/netzero/speaker/vi-VN/speaker-1.webp'},
  {src:'/image/netzero/speaker/vi-VN/speaker-1.webp'},
  {src:'/image/netzero/speaker/vi-VN/speaker-1.webp'},
  {src:'/image/netzero/speaker/vi-VN/speaker-1.webp'},
  {src:'/image/netzero/speaker/vi-VN/speaker-1.webp'},
  {src:'/image/netzero/speaker/vi-VN/speaker-1.webp'},
  {src:'/image/netzero/speaker/vi-VN/speaker-1.webp'}
];
const timeLine = computed(() => [
  {image:`/image/netzero/timeline/${locale.value}/timeline-one.webp`},
  {image:`/image/netzero/timeline/${locale.value}/timeline-3.webp`},
  {image:`/image/netzero/timeline/${locale.value}/timeline-2.webp`},
  {image:`/image/netzero/timeline/${locale.value}/timeline-4.webp`},
]);
const sponsorship = [
  {image:'/image/netzero/logo/elle.png'},
  {image:'/image/netzero/logo/kienviet.png'},
  {image:'/image/netzero/logo/cafef.png'}
];
const bus = [
  {image:'/image/netzero/bus/vi-VN/bus-1.webp'},
  {image:'/image/netzero/bus/vi-VN/bus-2.webp'}
];
const media = [
  {src:'/image/netzero/communication/1.png'},
  {src:'/image/netzero/communication/2.png'},
  {src:'/image/netzero/communication/3.png'},
  {src:'/image/netzero/communication/4.png'},
  {src:'/image/netzero/communication/5.png'},
  {src:'/image/netzero/communication/6.png'},
  {src:'/image/netzero/communication/7.png'},
  {src:'/image/netzero/communication/8.png'},
  {src:'/image/netzero/communication/9.png'},
  {src:'/image/netzero/communication/10.png'},
  {src:'/image/netzero/communication/11.png'},
  {src:'/image/netzero/communication/12.png'},
  {src:'/image/netzero/communication/13.png'},
  {src:'/image/netzero/communication/14.png'},
  {src:'/image/netzero/communication/15.png'},
  {src:'/image/netzero/communication/16.png'},
  {src:'/image/netzero/communication/17.png'},
  {src:'/image/netzero/communication/18.png'}
]


</script>
<style scoped>
.bg-main{
  background-image: url('/public/image/netzero/background/bg-main.jpg');
  background-size: cover;
  background-position: center;
};
.title-body {
  color: black;
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
.nav-item {
  position: relative;
}
.nav-item.active {
  color: #000000;
}
.nav-item.active:after,
.nav-item:hover:after {
  width: 100%;
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
}

</style>
