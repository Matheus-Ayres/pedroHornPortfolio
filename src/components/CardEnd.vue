<script setup>

const props = defineProps({
    title: String,
    icon: String,
    item1: String,
    item2: String,
    item3: String,
    item4: String,
    item5: String,
    item6: String
})

</script>


<template>
    <main class="relative bg-gradient-to-tl from-black to-purple-900
        h-90 w-64 flex justify-center items-start rounded-xl p-2 border-1 border-white">

        <div class="absolute left-1/2 -top-6 -translate-x-1/2
            w-16 h-16 bg-gradient-to-tr from-orange-700 via-black to-purple-600 via-50% rounded-full  shadow-lg
            flex justify-center items-center">
            <img :src="props.icon" class="w-7" />
        </div>

        <div class="flex flex-col text-center">

            <h1 class="text-Main text-white text-3xl mt-10 mb-5">
                {{ props.title }}
            </h1>

            <div class="flex flex-col text-Sec text-white text-center gap-3">
                <span>
                    {{ props.item1 }}
                </span>
                <span>
                    {{ props.item2 }}
                </span>
                <span>
                    {{ props.item3 }}
                </span>
                <span>
                    {{ props.item4 }}
                </span>
                <span>
                    {{ props.item5 }}
                </span>
                <span>
                    {{ props.item6 }}
                </span>
            </div>
        </div>
    </main>
</template>
