<script setup lang="ts">
import { RiHomeFill, RiSettingsFill, RiNotification4Fill, RiHeartFill } from '@remixicon/vue';
</script>

<template lang="html">
    <div class="sticky bg-white grid grid-cols-4 items-center justify-center h-16 w-full bottom-0 rounded-lg">
        <!-- Home Link -->
        <RouterLink class="flex justify-center items-center" to="/"
            :class="{ 'text-slate-400': !$route.path.endsWith('/home'), 'text-slate-800': $route.path.endsWith('/') }">
            <RiHomeFill size="20" />
            <div :class="{ 'w-5 h-5 absolute bg-slate-800 blur-xl rounded-full z-0': !$route.path.endsWith('/home') }">
            </div>
        </RouterLink>

        <!-- Favorites Link -->
        <RouterLink class="flex justify-center items-center" to="/favorites"
            :class="{ 'text-slate-400': !$route.path.startsWith('/favorites'), 'text-red-400': $route.path === '/favorites' }">
            <RiHeartFill size="20" />
            <div :class="{ 'w-5 h-5 absolute bg-red-500 blur-xl rounded-full z-0': $route.path === '/favorites' }">
            </div>
        </RouterLink>

        <!-- Notifications Link -->
        <RouterLink class="flex justify-center items-center" to="/notifications"
            :class="{ 'text-slate-400': !$route.path.startsWith('/notifications'), 'text-blue-500': $route.path === '/notifications' }">
            <RiNotification4Fill size="20" />
            <div :class="{ 'w-5 h-5 absolute bg-blue-500 blur-xl rounded-full z-0': $route.path === '/notifications' }">
            </div>
        </RouterLink>

        <!-- Settings Link -->
        <RouterLink class="flex justify-center items-center" to="/settings"
            :class="{ 'text-slate-400': !$route.path.startsWith('/settings'), 'text-orange-500': $route.path === '/settings' }">
            <RiSettingsFill size="20" />
            <div :class="{ 'w-5 h-5 absolute bg-orange-400 blur-xl rounded-full z-0': $route.path === '/settings' }">
            </div>
        </RouterLink>
    </div>
</template>
