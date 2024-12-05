<script setup lang="ts">
import {
    RiCupFill,
    RiLeafFill,
    RiPokerClubsFill,
    RiBlueskyFill,
    RiLandscapeAiFill,
    RiMapPin2Fill,
} from '@remixicon/vue'
import { ref } from 'vue'

// const props = defineProps({
//     Title: String,
//     Tabs: {
//         type: Array,
//         required: true,
//     },
// })

const tabs = [
    { label: 'Cafe', icon: RiCupFill },
    { label: 'Culture', icon: RiBlueskyFill },
    { label: 'Nature', icon: RiLeafFill },
    { label: 'Landscape', icon: RiLandscapeAiFill },
    { label: 'NightClub', icon: RiPokerClubsFill },
]

let selectedTab = ref(0)
</script>

<template lang="html">
    <p class="text-[13px] text-gray-800 font-medium mt-6">Select Your Interest</p>
    <ul class="grid grid-cols-5 gap-[6px] mt-2 text-gray-600">
        <li v-for="(tab, index) in tabs" :key="index" :class="[
            'flex justify-center items-center flex-col gap-[6px] rounded-md py-4 transition-all duration-500 ease-in-out cursor-pointer',
            selectedTab === index ? 'bg-[#1F2937] text-gray-300' : 'bg-white shadow-sm',
        ]" @click="selectedTab = index">
            <component :is="tab.icon" size="23" />
            <small class="text-[9px]">{{ tab.label }}</small>
        </li>
    </ul>

    <div class="flex justify-start items-center gap-1 text-[13px] mt-6 rounded-md p-[10px] bg-white">
        <RiMapPin2Fill size="18" class="text-gray-600" />
        <input class="bg-transparent p-1 outline-none text-gray-600" placeholder="Select your location" />
    </div>

    <div class="flex justify-between items-center text-gray-600 gap-1 text-[12px] mt-2 rounded-md">
        <span class="flex gap-1">
            <button class="rounded-full bg-white px-3 py-2">Mumbai</button>
            <button class="rounded-full bg-white px-3 py-2">Pune</button>
        </span>
        <select class="p-2 px-3 text-[11px] outline-none rounded-md border border-gray-800 text-gray-800 bg-transparent ">
            <option value="">More</option>
            <option value="">Pune</option>
            <option value="">Goa</option>

        </select>
    </div>
</template>
