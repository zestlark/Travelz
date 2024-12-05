<script setup lang="ts">
import PhoneScreen from '../components/PhoneScreen.vue'
import NavBar from '@/components/NavBar.vue'
import Interest from '@/components/Interest.vue'
import LocationScroller from '@/components/Location/LocationScroller.vue'
import Footer from '@/components/Footer.vue';
</script>

<template>
  <PhoneScreen>
    <NavBar />
    <p class="text-[13px] mt-4 text-gray-600">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Error, fugiat.
    </p>
    <Interest />
    <LocationScroller />
    <Footer/>
  </PhoneScreen>
</template>
