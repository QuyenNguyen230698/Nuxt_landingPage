<template>
  <div>
    <header class="bg-black hover:bg-white transition-colors duration-1000 ease-in-out sticky z-50 top-0 left-0 right-0 shadow w-full"
        :class="{'bg-white': isScrolled}">
            <div class="container mx-auto px-2 sm:px-4 lg:px-6 xl:px-8 animate-fade-down duration-1000 ease-in-out flex items-center justify-between h-8 sm:h-12 lg:h-16 xl:h-20 relative navbar">
                <div class="navbar-start h-8 sm:h-12 lg:h-16 xl:h-20">
                    <a href="#">
                        <img class="w-fit h-auto object-contain max-w-full max-h-full" src="/public/image/netzero/header/logo.png" alt="logo" />
                    </a>
                </div>
                <div class="navbar-end h-10 flex justify-end">
                    <div class="flex">
                        <div class="flex flex-col w-full h-full gap-6">
                            <div class="container mx-auto flex gap-6 text-white">
                            <button class="text-xs sm:text-sm md:text-base py-2 cursor-pointer">{{ $t('app.form.signEvent') }}</button>
                            <button class="text-xs sm:text-sm md:text-base py-2 cursor-pointer">{{ $t('app.form.signBooth') }}</button>
                            </div>
                        </div>
                        <div class="relative">
                            <LanguageSwitch/>
                        </div>
                    </div>
                </div>
            </div>
            <!-- hover header -->
            <div class="container mx-auto px-2 sm:px-4 lg:px-6 xl:px-8 flex items-center justify-between h-8 sm:h-12 lg:h-16 xl:h-20 absolute top-0 left-0 right-0 navbar opacity-0 hover:opacity-100 hover:z-50"
            :class="{'opacity-100': isScrolled}">
                <div class="navbar-start h-8 sm:h-12 lg:h-16 xl:h-20">
                    <a href="#">
                        <img class="w-fit h-auto object-contain max-w-full max-h-full" src="/public/image/netzero/header/logo-light.png" alt="logo" />
                    </a>
                </div>
                <div class="navbar-end h-10 flex justify-end">
                    <div class="flex">
                        <div class="flex flex-col w-full h-full gap-6">
                            <div class="container mx-auto flex gap-6">
                            <button @click="scrollToForm('participate')" class="nav-item text-xs sm:text-sm md:text-base py-2 cursor-pointer">{{ $t('app.form.signEvent') }}</button>
                            <button @click="scrollToForm('booth')" class="nav-item text-xs sm:text-sm md:text-base py-2 cursor-pointer">{{ $t('app.form.signBooth') }}</button>
                            </div>
                        </div>
                        <div class="relative">
                            <LanguageSwitch/>
                        </div>
                    </div>
                </div>
            </div>
        </header>
  <div class="relative w-full z-20 overflow-hidden flex flex-col">
    <img data-aos="fade-up" data-aos-duration='1000' data-aos-offset=“100” src="/public/image/netzero/header/banner.jpg" alt="" />
    <div class="bg-main w-full h-full relative flex flex-col">
      <div class="w-full h-full">
        <!-- header & section -->
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
      </div>
    </div>
    <!-- Time line -->
    <TimeLine :timeLine="timeLine" :background="background"/>
    <!-- Register -->
     <div class="relative w-full h-full flex flex-col py-6">
      <div class="container mx-auto flex gap-6">
        <button @click="showForm = 'participate'" :class="{'active': showForm === 'participate'}" data-aos="fade-up" data-aos-duration='1000' data-aos-offset=“100” class="text-xs sm:text-sm md:text-base nav-item py-2 cursor-pointer">{{ $t('app.form.signEvent') }}</button>
        <button @click="showForm = 'booth'" :class="{'active': showForm === 'booth'}" data-aos="fade-up" data-aos-duration='1200' data-aos-offset=“100” class="text-xs sm:text-sm md:text-base nav-item py-2 cursor-pointer">{{ $t('app.form.signBooth') }}</button>
      </div>
     </div>
     <div ref="areaForm" class="flex flex-col w-full h-full bg-black">
      <!-- form 1 -->
      <section v-if="showForm === 'participate'" class="container mx-auto flex flex-col overflow-hidden items-center bg-black">
        <div class="relative hero-module">
          <div class="relative grid-module">
            <div class="wrapper-container">
              <div class="grid lg:grid-cols-2 md:grid-cols-2 gap-5 py-8">
                <!-- image -->
                <div class="lg:col-span-1 col-auto md:order-2 order-2 text-center">
                  <img data-aos="fade-left" data-aos-duration='1000' data-aos-offset=“100” src="/public/image/netzero/form/image.jpg" class="w-full h-auto object-contain aspect-square">
                </div>
                <div class="lg:col-span-1 col-auto flex flex-col lg:items-start items-center justify-start md:order-1 order-1 text-right w-full">
                  <section class="w-full text-white bg-black">
                    <div class="flex flex-col gap-6 w-full">
                      <div class="grid grid-cols-1 gap-5 md:grid-cols-2 md:gap-4 w-full">
                        <div data-aos="fade-right" data-aos-duration='1000' data-aos-offset=“100” class="col-span-2">
                          <label class="block mb-1 font-light text-base">
                            <span class="text-base flex items-center text-center">
                              {{ $t('form.fullName') }}
                            </span>
                          </label>
                          <input type="text" :placeholder="$t('form.placeHolderName')" class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base">
                        </div>
                        <div data-aos="fade-right" data-aos-duration='1000' data-aos-offset=“100” class="col-span-2">
                          <label>
                            <span class="text-base flex items-center text-center">{{ $t('form.joinDate') }}</span>
                          </label>
                          <div class="grid grid-cols-2">
                            <div class="col-span-1">
                              <label class="flex items-start">
                                <input type="checkbox" class="checkbox text-sm border border-white rounded-full">
                                <p class="ml-3 cursor-pointer">21/11/2024</p>
                              </label>
                            </div>
                            <div class="col-span-1">
                              <label class="flex items-start">
                                <input type="checkbox"  class="checkbox text-sm border border-white rounded-full">
                                <p class="ml-3 cursor-pointer">22/11/2024</p>
                              </label>
                            </div>
                          </div>
                        </div>
                        <div data-aos="fade-right" data-aos-duration='1000' data-aos-offset=“100” class="col-span-2 lg:col-span-1">
                          <label class="block mb-1 font-light text-base">
                            <span class="text-base flex items-center text-center">
                              {{ $t('form.email') }}
                            </span>
                          </label>
                          <input type="email" :placeholder="$t('form.placeHolderEmail')" class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base">
                        </div>
                        <div data-aos="fade-right" data-aos-duration='1000' data-aos-offset=“100” class="col-span-2 lg:col-span-1">
                          <label class="block mb-1 font-light text-base">
                            <span class="text-base text-center flex items-center">
                              {{ $t('form.phone') }}
                            </span>
                          </label>
                          <input type="tel" :placeholder="$t('form.placeHolderPhone')" class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base">
                        </div>
                        <div data-aos="fade-right" data-aos-duration='1000' data-aos-offset=“100” class="col-span-2">
                          <label class="flex items-center">
                            <input type="checkbox" class="checkbox text-sm border border-white rounded-full">
                            <p class="ml-3 cursor-pointer">{{ $t('form.isStudent') }}</p>
                          </label>
                        </div>
                        <div data-aos="fade-right" data-aos-duration='1000' data-aos-offset=“100” class="col-span-2">
                          <label class="block mb-1 font-light text-base">
                            <span class="text-base flex items-center text-center">{{ $t('form.companyName') }}</span>
                          </label>
                          <input type="text" :placeholder="$t('form.companyName')" class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base">
                        </div>
                        <div data-aos="fade-right" data-aos-duration='1000' data-aos-offset=“100” class="col-span-2">
                          <label class="block mb-1 font-light text-base">
                            <span class="text-base flex items-center text-center">{{ $t('form.position') }}</span>
                          </label>
                          <input type="text" :placeholder="$t('form.position')" class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base">
                        </div>
                        <div data-aos="fade-right" data-aos-duration='1000' data-aos-offset=“100” class="col-span-2">
                          <label class="inline-flex items-center">
                            <span class="text-sm text-gray-400 text-justify">
                              {{ $t('form.textPolicy') }}
                            </span>
                          </label>
                        </div>
                        <div data-aos="fade-right" data-aos-duration='1000' data-aos-offset=“100” class="col-span-2 flex justify-center">
                          <button class="w-full btn bg-white rounded-none border-none text-black py-1 md:py-2 hover:bg-gray-600 hover:text-white transition-colors duration-300 ease-in-out">{{ $t('form.textButton') }}</button>
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
                  <img data-aos="fade-right" data-aos-duration='1000' data-aos-offset=“100” src="/public/image/netzero/form/booth.jpg" class="w-full h-auto object-contain aspect-square">
                </div>
                <div class="lg:col-span-1 col-auto flex flex-col lg:items-start items-center justify-start md:order-2 order-2 text-right w-full">
                  <section class="w-full text-white bg-black">
                    <div class="flex flex-col gap-6 w-full">
                      <div class="grid grid-cols-1 gap-5 md:grid-cols-2 md:gap-4 w-full">
                        <div data-aos="fade-left" data-aos-duration='1000' data-aos-offset=“100” class="col-span-2">
                          <label class="block mb-1 font-light text-base">
                            <span class="text-base flex items-center text-center">
                              {{ $t('form.fullName') }}
                            </span>
                          </label>
                          <input type="text" :placeholder="$t('form.placeHolderName')" class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base">
                        </div>
                        <div data-aos="fade-left" data-aos-duration='1000' data-aos-offset=“100” class="col-span-2">
                          <label class="block mb-1 font-light text-base">
                            <span class="text-base flex items-center text-center">
                              {{ $t('form.email') }}
                            </span>
                          </label>
                          <input type="email" :placeholder="$t('form.placeHolderEmail')" class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base">
                        </div>
                        <div data-aos="fade-left" data-aos-duration='1000' data-aos-offset=“100” class="col-span-2">
                          <label class="block mb-1 font-light text-base">
                            <span class="text-base text-center flex items-center">
                              {{ $t('form.phone') }}
                            </span>
                          </label>
                          <input type="tel" :placeholder="$t('form.placeHolderPhone')" class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base">
                        </div>
                        <div data-aos="fade-left" data-aos-duration='1000' data-aos-offset=“100” class="col-span-2">
                          <label class="block mb-1 font-light text-base">
                            <span class="text-base flex items-center text-center">
                              {{ $t('form.companyName') }}
                            </span>
                          </label>
                          <input type="text" :placeholder="$t('form.companyName')" class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base">
                        </div>
                        <div data-aos="fade-left" data-aos-duration='1000' data-aos-offset=“100” class="col-span-2">
                          <label class="block mb-1 font-light text-base">
                            <span class="text-base flex items-center text-center">
                              {{ $t('form.position') }}
                            </span>
                          </label>
                          <input type="text" :placeholder="$t('form.position')" class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base">
                        </div>
                        <div data-aos="fade-left" data-aos-duration='1000' data-aos-offset=“100” class="col-span-2">
                          <label class="inline-flex items-center">
                            <span class="text-sm text-gray-400 text-justify">
                              {{ $t('form.textPolicy') }}
                            </span>
                          </label>
                        </div>
                        <div data-aos="fade-left" data-aos-duration='1000' data-aos-offset=“100” class="col-span-2 flex justify-center">
                          <button class="w-full btn bg-white rounded-none border-none text-black py-1 md:py-2 hover:bg-gray-600 hover:text-white transition-colors duration-300 ease-in-out">{{ $t('form.textButton') }}</button>
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
        <div data-aos="fade-up" data-aos-duration='1000' data-aos-offset=“100” class="text-center uppercase font-bold text-xl md:text-2xl lg:text-3xl text-black bg-white py-6">
          <h2 class="title-body">{{ $t('app.partner.partner') }}</h2>
        </div>
        <div class="container w-full mx-auto px-4">
          <div class="grid grid-cols-2 lg:grid-cols-4 gap-6 overflow-x-hidden">
            <div data-aos="fade-up" data-aos-duration='900' data-aos-offset=“100” class="flex justify-center">
              <img src="" class="w-full h-auto max-h-16 min-h-16 object-contain bg-black">
            </div>
            <div data-aos="fade-up" data-aos-duration='1000' data-aos-offset=“100” class="flex justify-center">
              <img src="" class="w-full h-auto max-h-16 min-h-16 object-contain bg-black">
            </div>
            <div data-aos="fade-up" data-aos-duration='1100' data-aos-offset=“100” class="flex justify-center">
              <img src="" class="w-full h-auto max-h-16 min-h-16 object-contain bg-black">
            </div>
            <div data-aos="fade-up" data-aos-duration='1200' data-aos-offset=“100” class="flex justify-center">
              <img src="" class="w-full h-auto max-h-16 min-h-16 object-contain bg-black">
            </div>
          </div>
        </div>
      </div>
      <!-- Media sponsorship -->
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
       <!-- Media -->
         <div class="flex flex-col w-full h-full mt-2 mb-4">
          <div data-aos="fade-up" data-aos-duration='1000' data-aos-offset=“100” class="text-center uppercase font-bold text-xl md:text-2xl lg:text-3xl text-black bg-white py-6">
            <h2 class="title-body">{{ $t('app.media.communication') }}</h2>
          </div>
          <div class="flex w-full flex-col container mx-auto px-12">
            <ImageGallary :imageUrls="media" :useActive="false" :duration="1000" useGap="gap-6"/>
          </div>
         </div>
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
         <!-- Event Venue -->
         <div class="container mx-auto flex flex-col w-full h-full gap-6 mb-24">
            <div class="text-start uppercase font-bold text-xl md:text-2xl lg:text-3xl text-black bg-white py-6">
              <h2 data-aos="fade-up" data-aos-duration='1000' data-aos-offset=“100” class="title-body">{{ $t('app.event.venue') }}</h2>
            </div>
            <div class="flex w-full min-h-96 bg-black"></div>
          </div>
  </div>
       <footer class="relative z-10 bg-black w-full overflow-hidden">
            <footer class="container px-6 lg:px-0 mx-auto text-white">
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8 py-8 md:py-12 lg:py-8">
                    <div class="flex flex-col items-center lg:items-start">
                        <img data-aos="fade-up" data-aos-duration="800" data-aos-offset=“100” src="/public//image/logo/main.png" alt="" class="w-32 h-10 object-contain mb-4">
                        <nav data-aos="fade-up" data-aos-duration="1000" data-aos-offset=“100” class="flex space-x-4 mt-4">
                            <a href="#">
                                <i class="bi bi-facebook text-xl"></i>
                            </a>
                            <a href="#">
                                <i class="bi bi-youtube text-xl"></i>
                            </a>
                            <a href="#">
                                <i class="bi bi-instagram text-xl"></i>
                            </a>
                            <a href="#">
                                <i class="bi bi-linkedin text-xl"></i>
                            </a>
                        </nav>
                    </div>
                    <div class="lg:col-span-3 grid grid-cols-2 lg:grid-cols-3 gap-8 lg:items-start">
                        <nav data-aos="fade-up" data-aos-duration="800" data-aos-offset=“100” class="flex flex-col justify-start h-full">
                            <div class="cursor-pointer text-base mb-4">
                                <a href="#">{{ $t('footer.aboutUs') }}</a>
                            </div>
                        </nav>
                        <nav data-aos="fade-up" data-aos-duration="800" data-aos-offset=“100” class="flex flex-col justify-start h-full">
                            <div class="cursor-pointer text-base mb-4">
                                <a href="#">{{ $t('footer.news') }}</a>
                            </div>
                        </nav>
                        <nav data-aos="fade-up" data-aos-duration="800" data-aos-offset=“100” class="flex flex-col justify-start h-full">
                            <div class="cursor-pointer text-base mb-4">
                                <a href="#">{{ $t('footer.contact') }}</a>
                            </div>
                        </nav>
                        <nav data-aos="fade-up" data-aos-duration="900" data-aos-offset=“100” class="flex flex-col justify-start h-full">
                            <div>
                                <h3 class="text-base mb-4">{{ $t('footer.sustainability') }}</h3>
                                <ul class="space-y-2">
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">{{ $t('footer.environment') }}</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">{{ $t('footer.social') }}</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">{{ $t('footer.governance') }}</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">{{ $t('footer.netZero2030') }}</a>
                                    </li>
                                </ul>
                            </div>
                        </nav>
                        <nav data-aos="fade-up" data-aos-duration="900" data-aos-offset=“100” class="flex flex-col justify-start h-full">
                            <div>
                                <h3 class="text-base mb-4">{{ $t('footer.solutions') }}</h3>
                                <ul class="space-y-2">
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">{{ $t('footer.hospitalityFurniture') }}</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">{{ $t('footer.architectureAndConstruction') }}</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">{{ $t('footer.modularHomes') }}</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">{{ $t('footer.hospitalityManagement') }}</a>
                                    </li>
                                </ul>
                            </div>
                        </nav>
                        <nav data-aos="fade-up" data-aos-duration="900" data-aos-offset=“100” class="flex flex-col justify-start h-full">
                            <div>
                                <h3 class="text-base mb-4">{{ $t('footer.projects') }}</h3>
                                <ul class="space-y-2">
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">{{ $t('footer.category') }}</a>
                                    </li>
                                    <li>
                                        <a href="#" class="hover:underline cursor-pointer text-sm">{{ $t('footer.threeDTour') }}</a>
                                    </li>
                                </ul>
                            </div>
                        </nav>
                        <nav data-aos="fade-up" data-aos-duration="1000" data-aos-offset=“100” class="flex flex-col justify-start h-full">
                            <div class="cursor-pointer text-base mb-4">
                                <a href="#">{{ $t('footer.career') }}</a>
                            </div>
                        </nav>
                        <nav data-aos="fade-up" data-aos-duration="1000" data-aos-offset=“100” class="flex flex-col justify-start h-full">
                            <div class="cursor-pointer text-base mb-4">
                                <a href="#">{{ $t('footer.contest') }}</a>
                            </div>
                        </nav>
                        <nav data-aos="fade-up" data-aos-duration="1000" data-aos-offset=“100”  class="flex flex-col justify-start h-full">
                            <div class="cursor-pointer text-base mb-4">
                                <a href="#">{{ $t('footer.brochure') }}</a>
                            </div>
                        </nav>
                    </div>
                </div>
                <div class="py-2 text-gray-500">
                    <div class="flex flex-col lg:flex-row items-center justify-between text-sm test-gray-400">
                        <p>© 2024 TranDuc Corporation</p>
                    </div>
                </div>
            </footer>
        </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const { locale } = useI18n()
const showForm = ref('participate')
const setCurrentForm = (form) => {
  showForm.value = form
}
const areaForm = ref(null)
const scrollToForm = (form) => {
  setCurrentForm(form)
  if (form && areaForm.value) {
    const offset = 180;
    const elementPosition = areaForm.value.getBoundingClientRect().top + window.scrollY;
    window.scrollTo({top: elementPosition - offset, behavior: 'smooth'})
  }
}

const section = computed(() => [
  {image:`/image/netzero/section/${locale.value}/1.webp`},
  {image:`/image/netzero/section/${locale.value}/2fix.webp`},
  {image:`/image/netzero/section/${locale.value}/3.webp`},
  {image:`/image/netzero/section/${locale.value}/4.webp`},
]);
const background = [
  {image:'/image/netzero/background/bg-title.png'}
];
const workshop = computed(() => [
  {image:`/image/netzero/workshop/${locale.value}/workshop-1.webp`},
  {image:`/image/netzero/workshop/${locale.value}/workshop-2.webp`},
  {image:`/image/netzero/workshop/${locale.value}/workshop-3.webp`},
  {image:`/image/netzero/workshop/${locale.value}/workshop-4.webp`},
]);
const speaker = computed(() => [
  {src:`/image/netzero/speaker/${locale.value}/speaker-1.webp`},
  {src:`/image/netzero/speaker/${locale.value}/speaker-1.webp`},
  {src:`/image/netzero/speaker/${locale.value}/speaker-1.webp`},
  {src:`/image/netzero/speaker/${locale.value}/speaker-1.webp`},
  {src:`/image/netzero/speaker/${locale.value}/speaker-1.webp`},
  {src:`/image/netzero/speaker/${locale.value}/speaker-1.webp`}
]);
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
const bus = computed(() => [
  {image:`/image/netzero/bus/${locale.value}/bus-1.webp`},
  {image:`/image/netzero/bus/${locale.value}/bus-2.webp`}
]);
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

const isScrolled = ref(false)
const targetElement = ref(null) 

onMounted(() => {
    window.addEventListener('scroll', checkScrollHover);
})

onUnmounted(() => {
    window.removeEventListener('scroll', checkScrollHover);
})

const checkScrollHover = () => {
    if (window.scrollY > 50) {
        isScrolled.value = true;
    } else {
        isScrolled.value = false;
    }
}

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
