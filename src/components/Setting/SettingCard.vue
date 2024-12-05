<script setup lang="ts">
import { RiArrowRightSLine } from '@remixicon/vue';
import Toggle from '../ui/Toggle.vue';
import { ref } from 'vue';

const isToggled = ref(false);
</script>

<template lang="html">
    <ul class="bg-white rounded-md mt-6 text-sm text-slate-600 overflow-hidden">
        <li
            class="p-3 py-4 text-[13px] hover:bg-slate-300/40 min-h-12 flex justify-between items-center border-b last-of-type:border-none">
            <div>
                Account Settings
            </div>
            <RiArrowRightSLine size="18" />
        </li>
        <li
            class="p-3 py-4 text-[13px] hover:bg-slate-300/40 min-h-12 flex justify-between items-center border-b last-of-type:border-none">
            <div>
                Privacy Settings
            </div>
            <RiArrowRightSLine size="18" />
        </li>
        <li
            class="p-3 py-4 text-[13px] hover:bg-slate-300/40 min-h-12 flex justify-between items-center border-b last-of-type:border-none">
            <div>
                Notifications Settings
            </div>
            <RiArrowRightSLine size="18" />
        </li>
    </ul>

    <ul class="bg-white rounded-md mt-3 text-sm text-slate-600 overflow-hidden">
        <li
            class="p-3 py-4 text-[13px] hover:bg-slate-300/40 min-h-12 flex justify-between items-center border-b last-of-type:border-none">
            <div>
                Theme Settings {{ isToggled ? 'true' : 'false' }}
            </div>
            <Toggle v-model="isToggled" />
        </li>
        <li
            class="p-3 py-4 text-[13px] hover:bg-slate-300/40 min-h-12 flex justify-between items-center border-b last-of-type:border-none">
            <div>
                Security Settings
            </div>
            <RiArrowRightSLine size="18" />
        </li>
        <li
            class="p-3 py-4 text-[13px] hover:bg-slate-300/40 min-h-12 flex justify-between items-center border-b last-of-type:border-none">
            <div>
                Payment Settings
            </div>
            <RiArrowRightSLine size="18" />
        </li>
    </ul>
</template>
