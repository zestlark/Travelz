<script setup lang="ts">
import { RiBookmark3Fill, RiBuildingFill, RiDiscountPercentFill, RiPushpinFill } from '@remixicon/vue';
import type { PropType } from 'vue';
import { RouterLink } from 'vue-router';

const notificationIcon = {
    "location": {
        'icon': RiBuildingFill,
        'color': '#85A98F'
    },
    "booking": {
        'icon': RiBookmark3Fill,
        'color': '#DE7C7D'
    },
    "offer": {
        'icon': RiDiscountPercentFill,
        'color': '#F29F58'
    },
    "reminder": {
        'icon': RiPushpinFill,
        'color': '#54473F'
    },
}

export interface INotification { id: number; type: 'location' | 'booking' | 'offer' | 'reminder'; message: string; time: string; link: string; isRead: boolean; }

const props = defineProps({
    notificationData: {
        type: Object as PropType<INotification>,
        required: true,
    },
})
</script>

<template lang="html">
    <div
        :class="{ 'bg-white/40': !notificationData.isRead, 'rounded-md': false, 'border-b': true, 'border-b-slate-300': true, 'last-of-type:border-0': true }">
        <RouterLink :to="notificationData.link">
            <div class=" relative p-3 flex gap-2 text-slate-600 min-h-[70px]">
                <component :is="notificationIcon[notificationData.type].icon" size="28"
                    :style="{ background: notificationIcon[notificationData.type].color + 22, color: notificationIcon[notificationData.type].color }"
                    class="h-8 min-w-8 p-[6px] mt-[2px] rounded-md" />
                <div>
                    <p class="text-[12px] text-gray-500 leading-4">{{ notificationData.message }} </p>
                    <p class="text-xs text-slate-400"><small>{{ notificationData.time }}</small></p>
                </div>

                <div v-if="notificationData.isRead" class="h-2 w-2 absolute bg-red-400 -ml-[2px] -mt-[2px] rounded-full"></div>
            </div>
        </RouterLink>
    </div>
</template>