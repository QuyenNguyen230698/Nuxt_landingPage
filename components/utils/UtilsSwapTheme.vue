<template>
  <div class="flex items-center justify-center space-x-4">
    <div class="relative">
      <!-- Custom Dropdown Button -->
      <div @click="toggleDropdown"
        class="dropdown dropdown-end btn btn-primary btn-sm w-full cursor-pointer flex justify-between items-center"
        :class="{ 'min-w-[8rem]': true }">
        <span v-html="themes[selectedTheme].label"></span>
        <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4 ml-2" fill="none" viewBox="0 0 24 24"
          stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
        </svg>
      </div>
      <!-- Dropdown Content -->
      <ul v-if="isDropdownOpen" id="MenuTheme"
        class="absolute right-0 z-10 mt-2  border border-gray-200 rounded-md shadow-lg w-44 p-2">
        <li v-for="(theme, key) in themes" :key="key" @click="selectTheme(key)"
          class="flex items-center p-2 cursor-pointer w-full hover:bg-gray-300 rounded-md transition-all"
          id="MenuThemeItems">
          <span v-html="theme.label" class="font-medium flex-grow p-1"></span>
          <span v-html="theme.colors" class="flex items-center gap-1"></span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>

const emit = defineEmits(['updateTheme']);

const themes = {
  light: {
    label: 'Light',
    colors: `<span class="flex items-center gap-1">
              <span class="bg-primary rounded-full w-2 h-5"></span>
              <span class="bg-secondary rounded-full w-2 h-5"></span>
              <span class="bg-accent rounded-full w-2 h-5"></span>
              <span class="bg-neutral rounded-full w-2 h-5"></span>
            </span>`
  },
  dark: {
    label: 'Dark',
    colors: `<span class="flex items-center gap-1">
              <span class="bg-gray-800 rounded-full w-2 h-5"></span>
              <span class="bg-gray-900 rounded-full w-2 h-5"></span>
              <span class="bg-gray-700 rounded-full w-2 h-5"></span>
              <span class="bg-gray-600 rounded-full w-2 h-5"></span>
            </span>`
  },
  valentine: {
    label: 'Valentine',
    colors: `<span class="flex items-center gap-1">
              <span class="bg-pink-500 rounded-full w-2 h-5"></span>
              <span class="bg-red-500 rounded-full w-2 h-5"></span>
              <span class="bg-purple-500 rounded-full w-2 h-5"></span>
              <span class="bg-pink-300 rounded-full w-2 h-5"></span>
            </span>`
  },
  halloween: {
    label: 'Halloween',
    colors: `<span class="flex items-center gap-1">
              <span class="bg-orange-500 rounded-full w-2 h-5"></span>
              <span class="bg-black rounded-full w-2 h-5"></span>
              <span class="bg-purple-700 rounded-full w-2 h-5"></span>
              <span class="bg-yellow-500 rounded-full w-2 h-5"></span>
            </span>`
  },
  dracula: {
    label: 'Dracula',
    colors: `<span class="flex items-center gap-1">
              <span class="bg-purple-800 rounded-full w-2 h-5"></span>
              <span class="bg-red-600 rounded-full w-2 h-5"></span>
              <span class="bg-pink-700 rounded-full w-2 h-5"></span>
              <span class="bg-black rounded-full w-2 h-5"></span>
            </span>`
  },
  business: {
    label: 'Business',
    colors: `<span class="flex items-center gap-1">
              <span class="bg-gray-700 rounded-full w-2 h-5"></span>
              <span class="bg-blue-600 rounded-full w-2 h-5"></span>
              <span class="bg-gray-900 rounded-full w-2 h-5"></span>
              <span class="bg-blue-800 rounded-full w-2 h-5"></span>
            </span>`
  },
  winter: {
    label: 'Winter',
    colors: `<span class="flex items-center gap-1">
              <span class="bg-blue-300 rounded-full w-2 h-5"></span>
              <span class="bg-white rounded-full w-2 h-5"></span>
              <span class="bg-blue-500 rounded-full w-2 h-5"></span>
              <span class="bg-gray-100 rounded-full w-2 h-5"></span>
            </span>`
  },
};

const selectedTheme = ref(localStorage.getItem('selectedTheme') || 'light');
const isDropdownOpen = ref(false);
// Hàm đóng dropdown khi nhấp ra ngoài
const handleClickOutside = (event) => {
  const dropdownElement = document.querySelector('.relative');
  if (dropdownElement && !dropdownElement.contains(event.target)) {
    isDropdownOpen.value = false;
  }
};
const toggleDropdown = () => {
  isDropdownOpen.value = !isDropdownOpen.value;
};

const selectTheme = (themeKey) => {
  selectedTheme.value = themeKey;
  applyTheme(themeKey);
  isDropdownOpen.value = false;
};

const applyTheme = (theme) => {
  document.documentElement.setAttribute('data-theme', theme);
  localStorage.setItem('selectedTheme', theme);
  updateHeaderStyles();
};

const updateHeaderStyles = () => {
  const root = getComputedStyle(document.documentElement);
  const headerBgColor = root.getPropertyValue('--b1');
  const headerTextColor = root.getPropertyValue('--bc');
  const headerBgHoverColor = root.getPropertyValue('--er');
  const headerTextHoverColor = root.getPropertyValue('--sc');
  document.documentElement.style.setProperty('--header-bg-color', `oklch(${headerBgColor})`);
  document.documentElement.style.setProperty('--header-text-color', `oklch(${headerTextColor})`);


  // Áp dụng màu cho trạng thái hover
  document.documentElement.style.setProperty('--header-bg-hover-color', `oklch(${headerBgHoverColor})`);
  document.documentElement.style.setProperty('--header-text-hover-color', `oklch(${headerTextHoverColor})`);
};

onMounted(() => {
  applyTheme(selectedTheme.value);
  document.addEventListener('click', handleClickOutside);
  // Tìm tất cả các thẻ <span> có class 'e-searchbox e-fields'
});
// Loại bỏ sự kiện khi component bị unmounted
onBeforeUnmount(() => {
  document.removeEventListener('click', handleClickOutside);
});

watch(selectedTheme, (newTheme) => {
  emit('updateTheme', newTheme);
});
</script>


<style>
span.e-searchbox.e-fields {
    display: none !important;
}
li.e-submenu.e-menu-item{
    display: none !important;
}
#themeSelector {
  color: var(--header-text-color) !important;
}

#MenuTheme {
  color: var(--header-bg-color) !important;
  background-color: var(--header-text-color) !important;
}

#MenuThemeItems:hover {
  color: var(--header-bg-hover-color) !important;
  background-color: var(--header-text-hover-color) !important;
}

.e-grid .e-row:hover .e-rowcell {
  background-color: var(--header-bg-color) !important;
  color: var(--header-text-color) !important;
}

.e-searchbox {
  display: hidden !important;
}

.e-grid .e-rowcell.e-selectionbackground {
  background-color: var(--header-bg-color) !important;
  color: var(--header-text-color) !important;
}


.e-grid .e-headercell {
  background-color: var(--header-bg-color) !important;
  color: var(--header-text-color) !important;
  /* Sử dụng text-base */
  transition: var(--header-bg-color) 0.4s ease, color 0.4s ease;
  /* Thêm hiệu ứng chuyển màu */
  font-weight: bold;
}

.e-grid .e-gridheader {
  border-bottom-color: var(--header-text-color) !important;
  border-top-color: var(--header-text-color) !important;
}

.e-grid.e-resize-lines .e-headercell .e-rhandler,
.e-grid.e-resize-lines .e-headercell .e-rsuppress {
  border-right: 1px solid var(--header-text-color) !important;
}

.e-grid th.e-headercell[aria-sort=ascending] .e-headertext,
.e-grid th.e-headercell[aria-sort=descending] .e-headertext,
.e-grid th.e-headercell[aria-sort=ascending] .e-sortfilterdiv,
.e-grid th.e-headercell[aria-sort=descending] .e-sortfilterdiv {
  color: var(--header-text-color) !important;
  opacity: 1;
}

.e-grid .e-icons:not(.e-btn-icon) {
  color: var(--header-text-color) !important;
}

.e-grid .e-gridpager {
  border: none !important;
  background-color: var(--header-bg-color) !important;
  color: var(--header-text-color) !important;
  transition: background-color 0.3s ease, color 0.3s ease, padding 0.3s ease, border-color 0.3s ease;
  /* Sử dụng text-base */
}

.e-grid .e-gridpager .e-prevpagedisabled,
.e-grid .e-gridpager .e-prevpage,
.e-grid .e-gridpager .e-nextpage,
.e-grid .e-gridpager .e-nextpagedisabled,
.e-grid .e-gridpager .e-lastpagedisabled,
.e-grid .e-gridpager .e-lastpage,
.e-grid .e-gridpager .e-firstpage,
.e-grid .e-gridpager .e-firstpagedisabled {
  background-color: var(--header-bg-color) !important;
  color: var(--header-text-color) !important;
  /* Sử dụng text-base */
}



.e-grid .e-gridpager .e-numericitem {
  background-color: var(--header-bg-color) !important;
  color: var(--header-text-color) !important;
  /* Sử dụng text-base */
  cursor: pointer;
}

.e-grid .e-gridpager .e-numericitem:hover {
  background-color: var(--header-bg-color) !important;
  color: var(--header-text-color) !important;
  /* Sử dụng text-base */
}

.e-grid .e-gridpager .e-currentitem {
  background-color: var(--header-bg-color) !important;
  color: var(--header-text-color) !important;
}


.e-grid .e-sortnumber {
  background-color: var(--header-bg-color) !important;
  color: var(--header-text-color) !important;
  /* Sử dụng text-base */
}

.e-grid .e-filterbarcell {
  background-color: var(--header-bg-color) !important;
  color: var(--header-text-color) !important;
  /* Sử dụng text-base */
}

.e-grid .e-groupdroparea {
  background-color: var(--header-bg-color) !important;
  color: var(--header-text-color) !important;
  border-top-color: var(--header-text-color) !important;
  /* Sử dụng text-base */
}

.e-grid .e-toolbar {
  border-bottom: 0;
  border-left: 0;
  border-right: 0;
  border-top: 1px solid var(--header-text-color) !important;
  border-radius: 0;
}

.e-grid .e-toolbar-items {
  background-color: var(--header-bg-color) !important;
  color: var(--header-text-color) !important;
  /* Sử dụng text-base */
}

.e-grid .e-filterbarcell .e-input-group.e-input-focus {
  background-color: var(--header-bg-color) !important;
  color: var(--header-text-color) !important;
}


.e-grid .e-toolbar {
  padding: 0.5%;
  background-color: var(--header-bg-color) !important;
}

.e-grid .e-toolbar .e-btn,
.e-grid .e-toolbar .e-btn span {
  background-color: var(--header-bg-color) !important;
  color: var(--header-text-color) !important;
}

/* Paganaration */
.e-pager .e-pagercontainer {
  background-color: var(--header-bg-color) !important;
  border-color: var(--header-text-color) !important;
}

.e-pager .e-numericitem {
  background: var(--header-bg-color) !important;
  border-right-color: var(--header-text-color) !important;
  color: #111827;
}

.e-pager .e-prevpagedisabled,
.e-pager .e-prevpage,
.e-pager .e-nextpage,
.e-pager .e-nextpagedisabled,
.e-pager .e-lastpagedisabled,
.e-pager .e-lastpage,
.e-pager .e-firstpage,
.e-pager .e-firstpagedisabled {
  background-color: var(--header-bg-color) !important;
  color: #6b7280;
}

.e-pager .e-prevpagedisabled,
.e-pager .e-prevpage,
.e-pager .e-nextpage,
.e-pager .e-nextpagedisabled,
.e-pager .e-lastpagedisabled,
.e-pager .e-lastpage,
.e-pager .e-firstpage,
.e-pager .e-firstpagedisabled {
  background-color: var(--header-text-color) !important;
  color: #6b7280;
}

.e-pager .e-firstpage,
.e-pager .e-prevpage,
.e-pager .e-firstpagedisabled,
.e-pager .e-prevpagedisabled,
.e-pager .e-nextpage,
.e-pager .e-lastpage,
.e-pager .e-nextpagedisabled,
.e-pager .e-lastpagedisabled {
  border-right-color: #e5e7eb;
}

.e-pager .e-pagercontainer .e-firstpage,
.e-pager .e-pagercontainer .e-prevpage,
.e-pager .e-pagercontainer .e-firstpagedisabled,
.e-pager .e-pagercontainer .e-prevpagedisabled,
.e-pager .e-pagercontainer .e-nextpage,
.e-pager .e-pagercontainer .e-lastpage,
.e-pager .e-pagercontainer .e-nextpagedisabled,
.e-pager .e-pagercontainer .e-lastpagedisabled {
  border-color: var(--header-text-color) !important;
}

/* Search  */
/* Điều chỉnh cho nhóm input tìm kiếm */
.e-grid .e-input-group.e-search {
  background-color: var(--header-bg-color) !important;
  border-radius: 5px !important;
  padding: 5px;
  transition: background-color 0.3s ease, border-color 0.3s ease;
}

/* Điều chỉnh cho input tìm kiếm */
.e-grid .e-input-group.e-search .e-input.e-search {
  background-color: transparent !important;
  color: var(--header-text-color) !important;
  border: none !important;
  outline: none !important;
  transition: color 0.3s ease;
}

/* Điều chỉnh cho trạng thái focus của input */
.e-grid .e-input-group.e-search .e-input.e-search:focus:not(.e-success):not(.e-warning):not(.e-error),
.e-grid .e-input-group.e-search .e-input.e-search:focus:not(.e-success):not(.e-warning):not(.e-error):not(.e-input-group) {
  background-color: var(--focus-bg-color, var(--header-bg-color)) !important;
  color: var(--focus-text-color, var(--header-text-color)) !important;
  box-shadow: 0 0 5px var(--focus-border-color, var(--header-text-color)) !important;
  outline: none !important;
  transition: background-color 0.3s ease, border-color 0.3s ease, color 0.3s ease, box-shadow 0.3s ease;
}

/* Điều chỉnh cho icon tìm kiếm và xóa */
.e-grid .e-input-group.e-search .e-input-group-icon,
.e-grid .e-input-group.e-search .e-search-icon {
  color: var(--header-text-color) !important;
  cursor: pointer;
  transition: color 0.3s ease;
}

/* Điều chỉnh cho trạng thái hover trên các biểu tượng */
.e-grid .e-input-group.e-search .e-input-group-icon:hover,
.e-grid .e-input-group.e-search .e-search-icon:hover {
  color: var(--active-text-color, var(--header-bg-color)) !important;
}


/* Button Pagging */
.e-pager .e-currentitem,
.e-pager .e-currentitem:hover {
  background: #e5e7eb;
  color: var(--header-text-color) !important;
  opacity: 1;
}

.e-pager .e-focused {
  box-shadow: transparent !important;
}

.e-pager .e-numericitem.e-currentitem {
  border: 0.5px solid var(--header-text-color) !important;
  padding: 3.5px 11px 6px 10px;
}

/* Button Pagging */
/* Button Select item page  */

/* Button in toolbar */
.e-toolbar .e-toolbar-item .e-tbar-btn:focus {
  background: none;
  border-radius: 4px;
  color: var(--header-text-color) !important;
  ;
  border-color: #6b7280;
  border-style: solid;
  border-width: 0;
  box-shadow: 0 0 0 1px var(--header-text-color) !important;
}

/* CheckBox */
.e-checkbox-wrapper .e-frame.e-stop,
.e-css.e-checkbox-wrapper .e-frame.e-stop {
  background-color: var(--header-bg-color) !important;
  border-color: var(--header-bg-color) !important;
  color: var(--header-text-color) !important;
}

.e-checkbox-wrapper .e-frame.e-check,
.e-css.e-checkbox-wrapper .e-frame.e-check {
  background-color: var(--header-bg-color) !important;
  border-color: var(--header-bg-color) !important;
  color: var(--header-text-color) !important;
}

/* Button search filter  */
.e-input-group:not(.e-success):not(.e-warning):not(.e-error),
.e-input-group.e-control-wrapper:not(.e-success):not(.e-warning):not(.e-error) {
  border-color: var(--header-text-color) !important;
  box-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
}

.e-input-group.e-input-focus:not(.e-success):not(.e-warning):not(.e-error),
.e-input-group.e-control-wrapper.e-input-focus:not(.e-success):not(.e-warning):not(.e-error) {
  border-color: var(--header-text-color) !important;
  border-radius: 4px;
  box-shadow: 0 0 0 1px var(--header-text-color) !important;
}

.e-footer-content .e-btn.e-primary.e-flat:not([DISABLED]) {
  background: var(--header-bg-color) !important;
  border-color: var(--header-bg-color) !important;
  color: var(--header-text-color) !important;
}

.e-dropdown-btn:focus,
.e-dropdown-btn.e-btn:focus {
  box-shadow: 0 0 0 2px rgba(255, 255, 255, 0.95), 0 0 0 4px var(--header-text-color) !important;
}

.e-grid .e-input-group.e-search .e-input.e-search::placeholder {
  color: var(--placeholder-color, var(--header-text-color)) !important;
  transition: color 0.3s ease;
}
</style>
