<header
      class="bg-black hover:bg-white transition-colors duration-1000 ease-in-out sticky z-50 top-0 left-0 right-0 shadow w-full"
      :class="{ 'bg-white': isScrolled }"
    >
      <div
        class="container mx-auto px-2 sm:px-4 lg:px-6 xl:px-8 animate-fade-down duration-1000 ease-in-out flex items-center justify-between h-8 sm:h-12 lg:h-16 xl:h-20 relative navbar"
      >
        <div class="navbar-start h-8 sm:h-12 lg:h-16 xl:h-20">
          <a href="#">
            <img
              class="w-fit h-auto object-contain max-w-full max-h-full"
              src="/public/image/netzero/header/logo.png"
              alt="logo"
            />
          </a>
        </div>
        <div class="navbar-end h-10 flex justify-end">
          <div class="flex">
            <div class="flex flex-col w-full h-full gap-6">
              <div class="container mx-auto flex gap-6 text-white">
                <button
                  class="text-xs sm:text-sm md:text-base py-2 cursor-pointer"
                >
                  {{ $t("app.form.signEvent") }}
                </button>
                <button
                  class="text-xs sm:text-sm md:text-base py-2 cursor-pointer"
                >
                  {{ $t("app.form.signBooth") }}
                </button>
              </div>
            </div>
            <div class="relative">
              <LanguageSwitch />
            </div>
          </div>
        </div>
      </div>
      <!-- hover header -->
      <div
        class="container mx-auto px-2 sm:px-4 lg:px-6 xl:px-8 flex items-center justify-between h-8 sm:h-12 lg:h-16 xl:h-20 absolute top-0 left-0 right-0 navbar opacity-0 hover:opacity-100 hover:z-50"
        :class="{ 'opacity-100': isScrolled }"
      >
        <div class="navbar-start h-8 sm:h-12 lg:h-16 xl:h-20">
          <a href="#">
            <img
              class="w-fit h-auto object-contain max-w-full max-h-full"
              src="/public/image/netzero/header/logo-light.png"
              alt="logo"
            />
          </a>
        </div>
        <div class="navbar-end h-10 flex justify-end">
          <div class="flex">
            <div class="flex flex-col w-full h-full gap-6">
              <div class="container mx-auto flex gap-6">
                <button
                  @click="scrollToForm('participate')"
                  class="nav-item text-xs sm:text-sm md:text-base py-2 cursor-pointer"
                >
                  {{ $t("app.form.signEvent") }}
                </button>
                <button
                  @click="scrollToForm('booth')"
                  class="nav-item text-xs sm:text-sm md:text-base py-2 cursor-pointer"
                >
                  {{ $t("app.form.signBooth") }}
                </button>
              </div>
            </div>
            <div class="relative">
              <LanguageSwitch />
            </div>
          </div>
        </div>
      </div>
    </header>