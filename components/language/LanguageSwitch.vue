<template>
  <div class="flex justify-between items-center gap-5" ref="dropdownContainer">
    <details id="language" class="dropdown dropdown-end" ref="dropdown">
      <summary style="    width: 32px !important;
    height: 32px !important;
    padding-left: 0rem !important;
    padding-right: 0rem !important;"
        class="btn w-full shadow-none border-none bg-transparent hover:bg-transparent focus:bg-transparent">
        <NuxtImg class="w-8 h-8 aspect-square rounded-full shadow-xl"
          :src="`image/netzero/header/${locale === 'vi-VN' ? 'language-vi.png' : 'language-en.png'}`" />
      </summary>
      <ul class="menu dropdown-content bg-base-100 rounded z-40 w-40 mr-3 p-1 shadow">
        <li><button @click="selectLanguage('en-US')" class="custorm-btn w-full">
            <NuxtImg class="w-8 h-8 rounded-full" src="image/netzero/header/language-en.png" />
            <span class="font-[sans-serif] text-black focus:text-white"> English</span>
          </button>
        </li>
        <li><button @click="selectLanguage('vi-VN')" class="custorm-btn  w-full ">
            <NuxtImg class="w-8 h-8 rounded-full" src="image/netzero/header/language-vi.png" />
            <span class="font-[sans-serif] text-black "> Vietnamese</span>
          </button>
        </li>
      </ul>
    </details>
  </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import { useI18n } from 'vue-i18n'

const { locale } = useI18n()
const isVietnamese = ref(false)
const dropdown = ref(null)
const dropdownContainer = ref(null)

function selectLanguage(lang) {
  setLanguage(lang)
  closeDropdown()
}

function setLanguage(lang) {
  locale.value = lang
  localStorage.setItem('preferredLanguage', lang)
  isVietnamese.value = lang === 'vi-VN'
}

function closeDropdown() {
  if (dropdown.value) {
    dropdown.value.removeAttribute('open')
  }
}

function handleClickOutside(event) {
  if (dropdownContainer.value && !dropdownContainer.value.contains(event.target)) {
    closeDropdown()
  }
}

onMounted(() => {
  const savedLanguage = localStorage.getItem('preferredLanguage') || 'en-US'
  setLanguage(savedLanguage)
  document.addEventListener('click', handleClickOutside)
})

onBeforeUnmount(() => {
  document.removeEventListener('click', handleClickOutside)
})
</script>
<style lang="scss">
#language .menu li>*:not(ul, .menu-title, details, .btn):active,
.menu li>*:not(ul, .menu-title, details, .btn).active,
.menu li>details>summary:active {
  background-color: transparent !important;
  ;
  color: #222222 !important;
}
</style>
