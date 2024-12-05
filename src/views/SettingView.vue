<script setup lang="ts">
import NavBar from '@/components/NavBar.vue';
import PhoneScreen from '@/components/PhoneScreen.vue';
import SettingCard from '@/components/Setting/SettingCard.vue';
import SettingFooter from '@/components/Setting/SettingFooter.vue';
import { onMounted, ref } from 'vue';

const detailedNav = ref(false);

onMounted(() => {
    const detailedNavTimeOut = setTimeout(() => {
        detailedNav.value = true;
        clearTimeout(detailedNavTimeOut)
    }, 100);
});
</script>

<template lang="html">
    <PhoneScreen>
        <NavBar :detailed-nav="detailedNav" />
        <SettingCard />
        <SettingFooter />

    </PhoneScreen>
</template>