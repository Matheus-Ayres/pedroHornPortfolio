<script setup>
import { ref, computed, onMounted, onBeforeUnmount } from 'vue'

import img1 from '@/assets/images/FT_Moldura(1).png'
import img2 from '@/assets/images/FT_Moldura(2).png'
import img3 from '@/assets/images/FT_Moldura(3).png'

const images = [img1, img2, img3]
const current = ref(0)

const leftImg = computed(() =>
    images[(current.value - 1 + images.length) % images.length]
)

const centerImg = computed(() => images[current.value])

const rightImg = computed(() =>
    images[(current.value + 1) % images.length]
)

function next() {
    current.value = (current.value + 1) % images.length
}

function prev() {
    current.value = (current.value - 1 + images.length) % images.length
}

// autoplay
let interval = null

onMounted(() => {
    interval = setInterval(next, 3000)
})

onBeforeUnmount(() => {
    clearInterval(interval)
})
</script>


<template>
    <div class="relative w-full h-[520px] flex items-center justify-center overflow-visible">

        <!-- esquerda -->
        <img :src="leftImg" class="absolute z-0 h-[450px] w-[220px] object-cover rounded-2xl opacity-60 blur-[1px]
        -translate-x-[120px]" />

        <!-- direita -->
        <img :src="rightImg" class="absolute z-0 h-[450px] w-[220px] object-cover rounded-2xl opacity-60 blur-[1px]
        translate-x-[120px]" />

        <!-- CENTRAL com animação SLIDE -->
        <transition name="slide-central" mode="out-in">
            <img :key="centerImg" :src="centerImg"
                class="relative z-10 h-[450px] w-[260px] object-cover rounded-2xl shadow-2xl" />
        </transition>


    </div>
</template>

<style scoped>
.slide-central-enter-active,
.slide-central-leave-active {
    transition: all 0.3s cubic-bezier(0.22, 0.61, 0.36, 1);
}

.slide-central-enter-from {
    opacity: 0;
    transform: translateX(40px) scale(0.96);
}

.slide-central-enter-to {
    opacity: 1;
    transform: translateX(0) scale(1);
}

.slide-central-leave-from {
    opacity: 1;
    transform: translateX(0) scale(1);
}

.slide-central-leave-to {
    opacity: 0;
    transform: translateX(-40px) scale(0.96);
}
</style>
