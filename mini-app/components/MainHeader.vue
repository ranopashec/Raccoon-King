<template>
  <header class="grid grid-cols-2 gap-4 w-full px-4 bg-gray-900/50 rounded-lg">
    <div class="flex flex-col items-center justify-center gap-2 rounded-lg">
      <div class="flex flex-row justify-between items-center w-full">
        <!-- <img src="/avatar.png" alt="AvatarImage" class="w-6 h-6" /> -->
        <span class="text-xs font-medium text-white"> {{ nickName }}</span>
        <span class="text-xs font-medium text-white">( {{ userStatus[userLevel.value] }} )</span>
      </div>
      <div class="flex flex-col gap-1 w-full">
        <div class="w-full">
          <span class="text-xs font-medium text-white">rank {{ userLevel }}/5</span>
        </div>
        <div class="w-full rounded-full h-6 bg-gray-800">
          <div class="w-1/2 h-6 rounded-full bg-gradient-to-r from-purple-500 to-pink-400"></div>
        </div>
      </div>
    </div>

    <div class="flex flex-col items-center justify-center py-4 w-full rounded-lg">
      <span class="flex flex-row w-full justify-center items-center gap-1 py-2">
        <p class="text-base text-white font-semibold">{{ raccoonsPerSec }}</p>
        <img src="/coin.png" alt="Coin Image" class="w-4 h-4" />
        <p class="text-xm text-white font-semibold">/ s</p>
      </span>
      <div class="flex flex-row w-full justify-center items-center gap-1 py-2">
        <p class="text-base text-white font-semibold">{{ raccoons }}</p>
        <img src="/coin.png" alt="Coin Image" class="w-6 h-6" />
      </div>
    </div>
  </header>
</template>

<script setup>
import { inject, ref } from 'vue';

const raccoons = inject('raccoons');
const raccoonsPerSec = inject('raccoonsPerSec');
const nickName = inject('nickName');
const userLevel = inject('userLevel');
const userStatus = ref(['hobo', 'pleb', 'baron', 'king', 'sigma']);
</script>
