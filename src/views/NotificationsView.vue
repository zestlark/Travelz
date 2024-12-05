<script setup lang="ts">
import PhoneScreen from '../components/PhoneScreen.vue'
import NavBar from '@/components/NavBar.vue'
import { RiNotification4Line } from '@remixicon/vue';
import { notifications } from '@/components/Notifications/notification';
import NotificationCard from '@/components/Notifications/NotificationCard.vue';
</script>

<template lang="html">
    <PhoneScreen>
        <NavBar />

        <p v-if="notifications.length > 0" class="text-[13px] text-gray-800 font-medium mt-6">Your Notifications</p>
        <div class="grid grid-cols-1 gap-0 mt-2 rounded-md overflow-x-hidden">
            <NotificationCard v-if="notifications.length > 0" :notificationData="notification"
                v-for="(notification) in notifications" :key="notification.id" />
        </div>

        <!-- no noti -->
        <div v-if="notifications.length <= 0"
            class="h-[70vh] flex justify-center gap-5 items-center flex-col text-slate-400">
            <RiNotification4Line size="60" />
            <p class="text-xs">No Notifications Found</p>
        </div>
    </PhoneScreen>
</template>
