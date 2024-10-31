<template>
  <div>
    <!-- header -->
    <header
        class="animate-fade-down duration-1000 ease-in-out sticky z-50 top-0 left-0 right-0 shadow w-full group"
        :class="{'bg-black': !showHeader, 'bg-white': showHeader}"
    >
      <div
        class="lg:container mx-auto navbar flex flex-col lg:flex-row w-full items-center lg:justify-between"
      >
        <div
          class="lg:navbar-start h-16 min-h-16 py-0 w-full flex justify-between container"
        >
          <a href="/">
            <img
              class="w-fit h-auto object-contain max-w-full max-h-full"
              :src="showHeader ? '/image/netzero/header/logo-light.png' : '/image/netzero/header/logo.png'"
              alt="logo"
            />
          </a>
          <div class="lg:hidden">
            <LanguageSwitch />
          </div>
        </div>
        <div
          class="lg:navbar-end flex w-full items-center justify-center gap-4 border-t  lg:border-none h-10 z-10 lg:justify-end"
          :class="{'border-white': !showHeader, 'border-black': showHeader}"
        >
          <div
            :class="{'text-white': !showHeader, 'text-black': showHeader}"
            class="flex items-center justify-center gap-4 text-nowrap"
          >
            <button
              @click="scrollToForm('participate')"
              class="text-sm sm:text-sm md:text-base py-2 cursor-pointer nav-item"
            >
              {{ $t("app.form.signEvent") }}
            </button>
            <button
              @click="scrollToForm('booth')"
              class="text-sm sm:text-sm md:text-base py-2 cursor-pointer nav-item"
            >
              {{ $t("app.form.signBooth") }}
            </button>
          </div>
          <div class="hidden lg:block">
            <LanguageSwitch />
          </div>
        </div>
      </div>
    </header>
    <!-- main -->
    <div class="relative w-full z-20 overflow-hidden flex flex-col">
      <img
        data-aos="fade-up"
        data-aos-duration="1000"
        data-aos-offset="“100”"
        src="/public/image/netzero/header/banner.jpg"
        alt=""
      />
      <div class="bg-main w-full h-full relative flex flex-col">
        <div class="w-full h-full">
          <!-- section -->
          <Section :section="section" />
          <!-- workshop & speaker -->
          <WorkShopSpeaker :workshop="workshop" :background="background" />
          <!-- speaker -->
          <Speaker :speaker="speaker" :background="background" />
        </div>
      </div>
      <!-- Time line -->
      <TimeLine :timeLine="timeLine" :background="background" />
      <!-- Register -->
      <div class="relative w-full h-full flex flex-col py-6">
        <div class="container mx-auto flex gap-6">
          <button
            @click="showForm = 'participate'"
            :class="{ active: showForm === 'participate' }"
            data-aos="fade-up"
            data-aos-duration="1000"
            data-aos-offset="“100”"
            class="text-xs sm:text-sm md:text-base nav-item py-2 cursor-pointer"
          >
            {{ $t("app.form.signEvent") }}
          </button>
          <button
            @click="showForm = 'booth'"
            :class="{ active: showForm === 'booth' }"
            data-aos="fade-up"
            data-aos-duration="1200"
            data-aos-offset="“100”"
            class="text-xs sm:text-sm md:text-base nav-item py-2 cursor-pointer"
          >
            {{ $t("app.form.signBooth") }}
          </button>
        </div>
      </div>
      <div ref="areaForm" class="flex flex-col w-full h-full bg-black">
        <!-- form 1 -->
        <RegisterForm1 v-if="showForm === 'participate'" />
        <!-- form 2 -->
        <RegisterForm2 v-if="showForm === 'booth'" />
      </div>
      <!-- partner -->
      <Partner />
      <!-- Sponsorship -->
      <Sponsorship :sponsorship="sponsorship" />
      <!-- Media -->
      <Media :media="media" />
      <!-- Bus -->
      <Bus :bus="bus" />
      <!-- Event Venue -->
      <Venue />
    </div>
    <!-- footer -->
    <footer class="relative z-10 bg-black w-full overflow-hidden">
      <footer class="container px-6 lg:px-0 mx-auto text-white">
        <div
          class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8 py-8 md:py-12 lg:py-8"
        >
          <div class="flex flex-col items-center lg:items-start">
            <img
              data-aos="fade-up"
              data-aos-duration="800"
              data-aos-offset="“100”"
              src="/public//image/logo/main.png"
              alt=""
              class="w-32 h-10 object-contain mb-4"
            />
            <nav
              data-aos="fade-up"
              data-aos-duration="1000"
              data-aos-offset="“100”"
              class="flex space-x-4 mt-4"
            >
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
          <div
            class="lg:col-span-3 grid grid-cols-2 lg:grid-cols-3 gap-8 lg:items-start"
          >
            <nav
              data-aos="fade-up"
              data-aos-duration="800"
              data-aos-offset="“100”"
              class="flex flex-col justify-start h-full"
            >
              <div class="cursor-pointer text-base mb-4">
                <a href="#">{{ $t("footer.aboutUs") }}</a>
              </div>
            </nav>
            <nav
              data-aos="fade-up"
              data-aos-duration="800"
              data-aos-offset="“100”"
              class="flex flex-col justify-start h-full"
            >
              <div class="cursor-pointer text-base mb-4">
                <a href="#">{{ $t("footer.news") }}</a>
              </div>
            </nav>
            <nav
              data-aos="fade-up"
              data-aos-duration="800"
              data-aos-offset="“100”"
              class="flex flex-col justify-start h-full"
            >
              <div class="cursor-pointer text-base mb-4">
                <a href="#">{{ $t("footer.contact") }}</a>
              </div>
            </nav>
            <nav
              data-aos="fade-up"
              data-aos-duration="900"
              data-aos-offset="“100”"
              class="flex flex-col justify-start h-full"
            >
              <div>
                <h3 class="text-base mb-4">
                  {{ $t("footer.sustainability") }}
                </h3>
                <ul class="space-y-2">
                  <li>
                    <a
                      href="#"
                      class="hover:underline cursor-pointer text-sm"
                      >{{ $t("footer.environment") }}</a
                    >
                  </li>
                  <li>
                    <a
                      href="#"
                      class="hover:underline cursor-pointer text-sm"
                      >{{ $t("footer.social") }}</a
                    >
                  </li>
                  <li>
                    <a
                      href="#"
                      class="hover:underline cursor-pointer text-sm"
                      >{{ $t("footer.governance") }}</a
                    >
                  </li>
                  <li>
                    <a
                      href="#"
                      class="hover:underline cursor-pointer text-sm"
                      >{{ $t("footer.netZero2030") }}</a
                    >
                  </li>
                </ul>
              </div>
            </nav>
            <nav
              data-aos="fade-up"
              data-aos-duration="900"
              data-aos-offset="“100”"
              class="flex flex-col justify-start h-full"
            >
              <div>
                <h3 class="text-base mb-4">{{ $t("footer.solutions") }}</h3>
                <ul class="space-y-2">
                  <li>
                    <a
                      href="#"
                      class="hover:underline cursor-pointer text-sm"
                      >{{ $t("footer.hospitalityFurniture") }}</a
                    >
                  </li>
                  <li>
                    <a
                      href="#"
                      class="hover:underline cursor-pointer text-sm"
                      >{{ $t("footer.architectureAndConstruction") }}</a
                    >
                  </li>
                  <li>
                    <a
                      href="#"
                      class="hover:underline cursor-pointer text-sm"
                      >{{ $t("footer.modularHomes") }}</a
                    >
                  </li>
                  <li>
                    <a
                      href="#"
                      class="hover:underline cursor-pointer text-sm"
                      >{{ $t("footer.hospitalityManagement") }}</a
                    >
                  </li>
                </ul>
              </div>
            </nav>
            <nav
              data-aos="fade-up"
              data-aos-duration="900"
              data-aos-offset="“100”"
              class="flex flex-col justify-start h-full"
            >
              <div>
                <h3 class="text-base mb-4">{{ $t("footer.projects") }}</h3>
                <ul class="space-y-2">
                  <li>
                    <a
                      href="#"
                      class="hover:underline cursor-pointer text-sm"
                      >{{ $t("footer.category") }}</a
                    >
                  </li>
                  <li>
                    <a
                      href="#"
                      class="hover:underline cursor-pointer text-sm"
                      >{{ $t("footer.threeDTour") }}</a
                    >
                  </li>
                </ul>
              </div>
            </nav>
            <nav
              data-aos="fade-up"
              data-aos-duration="1000"
              data-aos-offset="“100”"
              class="flex flex-col justify-start h-full"
            >
              <div class="cursor-pointer text-base mb-4">
                <a href="#">{{ $t("footer.career") }}</a>
              </div>
            </nav>
            <nav
              data-aos="fade-up"
              data-aos-duration="1000"
              data-aos-offset="“100”"
              class="flex flex-col justify-start h-full"
            >
              <div class="cursor-pointer text-base mb-4">
                <a href="#">{{ $t("footer.contest") }}</a>
              </div>
            </nav>
            <nav
              data-aos="fade-up"
              data-aos-duration="1000"
              data-aos-offset="“100”"
              class="flex flex-col justify-start h-full"
            >
              <div class="cursor-pointer text-base mb-4">
                <a href="#">{{ $t("footer.brochure") }}</a>
              </div>
            </nav>
          </div>
        </div>
        <div class="py-2 text-gray-500">
          <div
            class="flex flex-col lg:flex-row items-center justify-between text-sm test-gray-400"
          >
            <p>© 2024 TranDuc Corporation</p>
          </div>
        </div>
      </footer>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted, watch, nextTick, onBeforeMount } from 'vue';

const { locale } = useI18n();
const showForm = ref("participate");
const setCurrentForm = (form) => {
  showForm.value = form;
};

const showHeader = ref(false);
const scrollY = ref(0);

// Sửa lại hàm resetScroll
const resetScroll = async () => {
  await nextTick();
  window.scrollTo(0, 0);
  showHeader.value = false;
  scrollY.value = 0;
};

// Thêm onBeforeMount
onBeforeMount(() => {
  resetScroll();
});

const updateScroll = () => {
  scrollY.value = window.scrollY;
  if (scrollY.value > 50) {
    showHeader.value = true;
  } else {
    showHeader.value = false;
  }
};

const areaForm = ref(null);
const scrollToForm = (form) => {
  setCurrentForm(form);
  if (form && areaForm.value) {
    const offset = 180;
    const elementPosition =
      areaForm.value.getBoundingClientRect().top + window.scrollY;
    window.scrollTo({ top: elementPosition - offset, behavior: "smooth" });
  }
};

const section = computed(() => [
  { image: `/image/netzero/section/${locale.value}/1.webp` },
  { image: `/image/netzero/section/${locale.value}/2fix.webp` },
  { image: `/image/netzero/section/${locale.value}/3.webp` },
  { image: `/image/netzero/section/${locale.value}/4.webp` },
]);
const background = [{ image: "/image/netzero/background/bg-title.png" }];
const workshop = computed(() => [
  { image: `/image/netzero/workshop/${locale.value}/workshop-1.webp` },
  { image: `/image/netzero/workshop/${locale.value}/workshop-2.webp` },
  { image: `/image/netzero/workshop/${locale.value}/workshop-3.webp` },
  { image: `/image/netzero/workshop/${locale.value}/workshop-4.webp` },
]);
const speaker = computed(() => [
  { src: `/image/netzero/speaker/${locale.value}/speaker-1.webp` },
  { src: `/image/netzero/speaker/${locale.value}/speaker-1.webp` },
  { src: `/image/netzero/speaker/${locale.value}/speaker-1.webp` },
  { src: `/image/netzero/speaker/${locale.value}/speaker-1.webp` },
  { src: `/image/netzero/speaker/${locale.value}/speaker-1.webp` },
  { src: `/image/netzero/speaker/${locale.value}/speaker-1.webp` },
]);
const timeLine = computed(() => [
  { image: `/image/netzero/timeline/${locale.value}/timeline-one.webp` },
  { image: `/image/netzero/timeline/${locale.value}/timeline-3.webp` },
  { image: `/image/netzero/timeline/${locale.value}/timeline-2.webp` },
  { image: `/image/netzero/timeline/${locale.value}/timeline-4.webp` },
]);
const sponsorship = [
  { image: "/image/netzero/logo/elle.png" },
  { image: "/image/netzero/logo/kienviet.png" },
  { image: "/image/netzero/logo/cafef.png" },
];
const bus = computed(() => [
  { image: `/image/netzero/bus/${locale.value}/bus-1.webp` },
  { image: `/image/netzero/bus/${locale.value}/bus-2.webp` },
]);
const media = [
  { src: "/image/netzero/communication/1.png" },
  { src: "/image/netzero/communication/2.png" },
  { src: "/image/netzero/communication/3.png" },
  { src: "/image/netzero/communication/4.png" },
  { src: "/image/netzero/communication/5.png" },
  { src: "/image/netzero/communication/6.png" },
  { src: "/image/netzero/communication/7.png" },
  { src: "/image/netzero/communication/8.png" },
  { src: "/image/netzero/communication/9.png" },
  { src: "/image/netzero/communication/10.png" },
  { src: "/image/netzero/communication/11.png" },
  { src: "/image/netzero/communication/12.png" },
  { src: "/image/netzero/communication/13.png" },
  { src: "/image/netzero/communication/14.png" },
  { src: "/image/netzero/communication/15.png" },
  { src: "/image/netzero/communication/16.png" },
  { src: "/image/netzero/communication/17.png" },
  { src: "/image/netzero/communication/18.png" },
];

onMounted(() => {
  resetScroll();
  window.addEventListener("scroll", updateScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", updateScroll);
});

watch(scrollY, (newVal) => {
  if (newVal > 50) {
    showHeader.value = true;
  }
});
</script>
<style scoped>
.bg-main {
  background-image: url("/public/image/netzero/background/bg-main.jpg");
  background-size: cover;
  background-position: center;
}
.title-body {
  color: black;
  text-transform: uppercase;
  --tw-text-opacity: 1;
  font-weight: bold;
  font-size: 2.25rem;
  line-height: 2.5rem;
}
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
  height: 0.125rem;
  left: 0;
  position: absolute;
  width: 0;
  --tw-bg-opacity: 1;
  background-color: rgb(34 34 34 / var(--tw-bg-opacity));
  transition-duration: 0.5s;
  transition-property: all;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
}
</style>
