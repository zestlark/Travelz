<script setup lang="ts">
import { RiCopperCoinFill } from '@remixicon/vue';


const props = defineProps({
  detailedNav: {
    type: Boolean,
    required: false,
    default: false
  }
})

</script>
<template lang="html">
  <div class="flex justify-between gap-1 items-center mt-2">
    <div class="max-w-[calc(100%-104px)]">
      <h4 class="font-bold text-[21px]">Hi, Deepak</h4>
      <p v-if="detailedNav" class="text-xs text-slate-600 mt-1 line-clamp-1">kanojiyadeepak747@gmail.com</p>
      <div v-if="detailedNav"
        class="inline-flex bg-orange-400/20 text-orange-500 p-1 px-2 mt-[6px] justify-center items-center gap-1 rounded-full text-sm">
        <RiCopperCoinFill size="14" />
        <p class="text-[11px]">20 coins</p>
      </div>
    </div>
    <RouterLink to="/settings">
      <img
      :class="{ 'w-8': !detailedNav, 'h-8': !detailedNav, 'rounded-md': !detailedNav,'rounded-full': detailedNav, 'w-24': detailedNav, 'h-24': detailedNav, 'transition-all': true, 'duration-500': true }"
      src="https://avatarfiles.alphacoders.com/374/374791.png" />
    </RouterLink>
  </div>
</template>
