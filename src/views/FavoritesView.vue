<script setup lang="ts">
import PhoneScreen from '../components/PhoneScreen.vue'
import NavBar from '@/components/NavBar.vue'
import LocationCard from '@/components/Location/LocationCard.vue';
import { locationsData } from '@/components/Location/location';
import { RiHeartLine } from '@remixicon/vue';
import { computed } from 'vue';

const filteredLocations = computed(() => {
    return locationsData.filter((item) => item.favorite);
});

</script>

<template>
    <PhoneScreen>
        <NavBar />

        <!--  with fv -->
        <p v-if="filteredLocations.length > 0" class="text-[13px] text-gray-800 font-medium mt-6">Your Favorites</p>
        <div class="grid grid-cols-1 gap-2 mt-2">
            <LocationCard v-if="filteredLocations.length > 0" v-for="(item, index) in filteredLocations" :key="index"
                :width="'100%'" :location="item" />
        </div>

        <!-- no fav -->
        <div class="h-[70vh] flex justify-center gap-5 items-center flex-col text-slate-400"
            v-if="filteredLocations.length <= 0">
            <RiHeartLine size="60" />
            <p class="text-xs">No Favorites Found</p>
        </div>

    </PhoneScreen>
</template>
