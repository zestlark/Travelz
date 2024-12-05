<script setup lang="ts">
import BottomBar from './BottomBar.vue';
import InAnimation from './ui/InAnimation.vue';
</script>
<template lang="html">
    <div class="bg-slate-200 flex sm:min-h-[100svh] sm:w-screen justify-center items-center">
        <div
            class="w-full sm:w-[320px] max-h-[calc(100svh)] sm:h-[600px] shadow-2xl bg-slate-100 md:rounded-2xl overflow-scroll">
            <div class="p-4 min-h-[calc(100vh-64px)] sm:min-h-[calc(600px-64px)]">
                <InAnimation/>
                <slot></slot>
            </div>
            <BottomBar />
        </div>
    </div>
</template>
