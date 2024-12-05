<script setup lang="ts">
import { defineProps, defineEmits } from 'vue';

const props = defineProps({
    modelValue: {
        type: Boolean,
        default: false
    }
});

const emit = defineEmits(['update:modelValue']);

const toggle = () => {
    emit('update:modelValue', !props.modelValue);
};
</script>

<template lang="html">
    <div class="relative inline-block w-10 h-6 rounded-full cursor-pointer" :class="{
        'bg-green-500': modelValue,
        'bg-gray-300': !modelValue
    }" @click="toggle">
        <div class="absolute top-0 m-1 left-0 w-4 h-4 bg-white rounded-full transition-all duration-300"
            :style="{ transform: modelValue ? 'translateX(100%)' : 'translateX(0)' }"></div>
    </div>
</template>
