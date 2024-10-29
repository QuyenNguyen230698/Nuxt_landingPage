<template>
    <div class="flex items-center justify-center w-full" data-aos="fade-up" :data-aos-delay="100" data-aos-offset="10">
        <div ref="sidebar" class="scroll-smooth  w-full flex items-center justify-start overflow-y-hidden z-40">
            <div class="flex flex-nowrap w-full" :class="[useGap]">
                <div v-for="(itemImage, index) in images" :key="index" class="shrink-0 w-full"
                    :class="[cssWidth, useActive ? selectedImageIndex === index ? 'border-b border-primary transform-x duration-500 ease-linear' : '' : '']">
                    <NuxtImg :alt="`image-${index}`" quality="85" :src="changeUrl(itemImage.src.src)"
                        class="w-full h-full object-cover" format="webp" loading="eager" priority @load="itemImage.loading = false"
                        @error="itemImage.loading = false" />
                    <div v-if="itemImage.loading"
                        class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-30">
                        <span class="loading loading-infinity text-white w-8 h-8"></span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
const { locale } = useI18n()

//#region Anhld(Định nghĩa props)
const props = defineProps({
    imageUrls: {
        type: Array,
        required: true
    },
    cssWidth: {
        type: String,
        default: () => 'w-1/3 lg:w-1/4'
    },
    useActive: {
        type: Boolean,
        default: () => false
    },
    useGap: {
        type: String,
        default: () => ''
    },
    duration: {
        type: Number,
        default: () => 2000
    }
});
//#endregion
//#region Anhld(Khởi tạo các biến)

const images = ref([...props.imageUrls.map(url => ({ src: url, loading: true }))]);
const selectedImageIndex = ref(0);
const sidebar = ref(null);
const direction = ref(1);
const changeUrl = (url) => {
    const newUrl = url.replace(/(vi-VN|en-US)/g, locale.value);
    return newUrl
}
//#endregion

//#region Anhld(Hàm lấy đường dẫn ảnh)
//#endregion
//#region Anhld(Hàm cuộn đến ảnh được chọn)
const scrollToSelectedImage = () => {
    const imageElements = sidebar.value.querySelectorAll('img');
    const selectedImageElement = imageElements[selectedImageIndex.value];
    if (selectedImageElement) {
        selectedImageElement.scrollIntoView({
            behavior: 'smooth',
            block: 'nearest',
            inline: 'end'
        });
    }
};
//#endregion

//#region Anhld(Hàm chuyển ảnh tiếp theo)
const nextImage = () => {
    if (direction.value === 1) {
        if (selectedImageIndex.value < images.value.length - 1) {
            selectedImageIndex.value += 1;
        } else {
            direction.value = -1;
            selectedImageIndex.value -= 1;
        }
    } else if (direction.value === -1) {
        if (selectedImageIndex.value > 0) {
            selectedImageIndex.value -= 1;
        } else {
            direction.value = 1;
            selectedImageIndex.value += 1;
        }
    }
};
//#endregion

//#region Anhld(Tự động chuyển ảnh)
const autoRunImage = () => {
    const isSidebarInView = () => {
        const rect = sidebar.value?.getBoundingClientRect();
        return rect && rect.top >= 0 && rect.bottom <= window.innerHeight;
    };

    let intervalId;

    const toggleAutoNextImage = () => {
        if (isSidebarInView()) {
            if (!intervalId) {
          
                intervalId = setInterval(() => nextImage(), props.duration);
            }
        } else if (intervalId) {
            clearInterval(intervalId);
            intervalId = null;
        }
    };

    window.addEventListener('scroll', toggleAutoNextImage);

    onUnmounted(() => {
        clearInterval(intervalId);
        window.removeEventListener('scroll', toggleAutoNextImage);
    });
};
//#endregion

onMounted(() => {
    autoRunImage();
});

//#region Anhld(Theo dõi thay đổi)
watchEffect(() => {
    images.value.forEach(image => {
        if (image.loading === undefined) {
            image.loading = true;
        }
    });
});

watch(selectedImageIndex, () => scrollToSelectedImage());
//#endregion
</script>
<style>
.scroll-smooth {
    scroll-behavior: smooth !important;
}

.scroll-smooth::-webkit-scrollbar {
    width: 0 !important;
    /* Ẩn thanh cuộn trên Chrome, Safari, Opera */
    height: 0 !important;
    /* Ẩn thanh cuộn ngang nếu có */
    display: none !important;
}

.scroll-smooth {
    -ms-overflow-style: none !important;
    /* Ẩn thanh cuộn trên Internet Explorer và Edge */
    scrollbar-width: none !important;
    /* Ẩn thanh cuộn trên Firefox */
}
</style>
