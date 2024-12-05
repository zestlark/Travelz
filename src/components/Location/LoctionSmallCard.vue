<script setup lang="ts">
import { RiStarFill, RiHeartLine, RiHeartFill } from '@remixicon/vue'

const props = defineProps({
    location: {
        type: Object,
        required: true,
    },
    width: {
        type: String,
        required: false,
        default: '100%'
    }
})
</script>
<template lang="html">
    <div class="snap-start bg-white rounded-md overflow-hidden inline-block mr-2 last-of-type:mr-0 cursor-pointer"
        :style="{ width: width }">
        <div class="relative h-[180px]">
            <img class="h-full w-full object-cover" :src="location.image" />
            <div
                class="bg-gradient-to-t to-transparent via-transparent from-white absolute bottom-0 left-0 min-h-20 min-w-full">
            </div>
            <div class="absolute top-0 p-2 m-2 rounded-md text-slate-600 right-0 bg-white/40 backdrop-blur-md">
                <RiHeartLine v-if="!location.favorite" size="20" />
                <RiHeartFill v-if="location.favorite" size="20" class="text-red-400" />
            </div>
        </div>
        <div class="flex p-3 gap-2">
            <div class="block">
                <h5 class="text-sm font-medium text-gray-800">{{ location.name }}</h5>
                <p class="text-[10px] leading-3 whitespace-normal line-clamp-2 text-gray-600">
                    {{ location.description }}
                </p>
                <div
                    class="text-[12px] text-slate-500  mt-1 flex items-center gap-1">
                    <RiStarFill size="16" />
                    <span>{{ location.rating }}</span>
                </div>
                <!-- <p class="text-md text-blue-500 font-medium mt-1">
                    {{ location.price }} <sup class="text-[11px] uppercase">inr</sup>
                </p> -->
            </div>
        </div>
    </div>
</template>
