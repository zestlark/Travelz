<script setup lang="ts">
import { ref, onMounted } from 'vue';

let myheight = ref(0);

onMounted(() => {
    setTimeout(() => {
        myheight.value = 0;
    }, 0);
});
</script>

<template lang="html">
    <div :style="{ height: myheight + 'px' }" class="transition-all duration-0">
    </div>
</template>
