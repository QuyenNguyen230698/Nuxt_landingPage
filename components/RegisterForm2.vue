<template>
  <!-- form 2 -->
  <section
    class="container mx-auto flex flex-col overflow-hidden items-center bg-black"
  >
    <div class="relative hero-module">
      <div class="relative grid-module">
        <div class="wrapper-container">
          <div class="grid lg:grid-cols-2 md:grid-cols-2 gap-5 py-8">
            <!-- image -->
            <div class="lg:col-span-1 col-auto md:order-1 order-1 text-center">
              <img
                data-aos="fade-right"
                data-aos-duration="1000"
                data-aos-offset="“100”"
                src="/public/image/netzero/form/booth.jpg"
                class="w-full h-auto object-contain aspect-square"
              />
            </div>
            <div
              class="lg:col-span-1 col-auto flex flex-col lg:items-start items-center justify-start md:order-2 order-2 text-right w-full"
            >
              <section class="w-full text-white bg-black">
                <div class="flex flex-col gap-6 w-full">
                  <div
                    class="grid grid-cols-1 gap-5 md:grid-cols-2 md:gap-4 w-full"
                  >
                    <div
                      data-aos="fade-left"
                      data-aos-duration="1000"
                      data-aos-offset="“100”"
                      class="col-span-2"
                    >
                      <label class="block mb-1 font-light text-base">
                        <span class="text-base flex items-center text-center">
                          {{ $t("form.fullName") }}
                        </span>
                      </label>
                      <input
                        type="text"
                        :placeholder="$t('form.placeHolderName')"
                        class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base"
                      />
                    </div>
                    <div
                      data-aos="fade-left"
                      data-aos-duration="1000"
                      data-aos-offset="“100”"
                      class="col-span-2"
                    >
                      <label class="block mb-1 font-light text-base">
                        <span class="text-base flex items-center text-center">
                          {{ $t("form.email") }}
                        </span>
                      </label>
                      <input
                        type="email"
                        :placeholder="$t('form.placeHolderEmail')"
                        class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base"
                      />
                    </div>
                    <div
                      data-aos="fade-left"
                      data-aos-duration="1000"
                      data-aos-offset="“100”"
                      class="col-span-2"
                    >
                      <label class="block mb-1 font-light text-base">
                        <span class="text-base text-center flex items-center">
                          {{ $t("form.phone") }}
                        </span>
                      </label>
                      <input
                        type="tel"
                        :placeholder="$t('form.placeHolderPhone')"
                        class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base"
                      />
                    </div>
                    <div
                      data-aos="fade-left"
                      data-aos-duration="1000"
                      data-aos-offset="“100”"
                      class="col-span-2"
                    >
                      <label class="block mb-1 font-light text-base">
                        <span class="text-base flex items-center text-center">
                          {{ $t("form.companyName") }}
                        </span>
                      </label>
                      <input
                        type="text"
                        :placeholder="$t('form.companyName')"
                        class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base"
                      />
                    </div>
                    <div
                      data-aos="fade-left"
                      data-aos-duration="1000"
                      data-aos-offset="“100”"
                      class="col-span-2"
                    >
                      <label class="block mb-1 font-light text-base">
                        <span class="text-base flex items-center text-center">
                          {{ $t("form.position") }}
                        </span>
                      </label>
                      <input
                        type="text"
                        :placeholder="$t('form.position')"
                        class="w-full bg-transparent border-b border-gray-500 focus:outline-none py-1 text-base"
                      />
                    </div>
                    <div
                      data-aos="fade-left"
                      data-aos-duration="1000"
                      data-aos-offset="“100”"
                      class="col-span-2"
                    >
                      <label class="inline-flex items-center">
                        <span class="text-sm text-gray-400 text-justify">
                          {{ $t("form.textPolicy") }}
                        </span>
                      </label>
                    </div>
                    <div
                      data-aos="fade-left"
                      data-aos-duration="1000"
                      data-aos-offset="“100”"
                      class="col-span-2 flex justify-center"
                    >
                      <button
                        class="w-full btn bg-white rounded-none border-none text-black py-1 md:py-2 hover:bg-gray-600 hover:text-white transition-colors duration-300 ease-in-out"
                      >
                        {{ $t("form.textButton") }}
                      </button>
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
</template>

<script setup></script>

<style scoped></style>
