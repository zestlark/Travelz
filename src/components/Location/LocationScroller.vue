<script setup lang="ts">
import { onMounted, ref } from 'vue';
import LocationCard from './LocationCard.vue'
import { locationsData } from './location'
import { animate } from "motion/mini"
import LoctionSmallCard from './LoctionSmallCard.vue';

const containerRef = ref<HTMLElement | null>(null);

onMounted(() => {
  if (containerRef.value) {
    animate(containerRef.value, {
      opacity: [0, 1],
      transform: ['scale(0.5)', 'scale(1)'],
    });
  }
});
</script>

<template lang="html">
  <div class="mt-5 overflow-auto whitespace-nowrap rounded-md snap-x">
    <LocationCard width="210px" v-for="(location, index) in locationsData.slice(0, 4)" :key="index"
      :location="location" />
  </div>

  <div class="mt-5 ">
    <p class="text-[13px] text-gray-800 font-medium mt-6">Famous Places</p>
    <div class="grid grid-cols-2 gap-2 mt-2">
      <LoctionSmallCard v-for="(location, index) in locationsData.slice(4, -1)" :key="index" :location="location" />
    </div>

  </div>
</template>
