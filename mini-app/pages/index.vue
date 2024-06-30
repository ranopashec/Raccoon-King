<template>
  <div>
    <main
      class="font-sans min-h-screen touch-pan-x touch-pan-y py-4 px-4 bg-gradient-to-r from-0% via-50% to-100% from-black via-purple-950 to-black"
    >
      <MainHeader />
      <div class="flex flex-col items-center justify-center gap-8 mx-auto">
        <div class="flex flex-row w-full justify-center items-center gap-2 mt-8">
          <img src="/coin.png" alt="Coin Image" class="w-8 h-8" />
          <p class="text-3xl text-white font-semibold">{{ raccoons }} RCN</p>
        </div>

        <button
          @click="tap"
          class="w-60 h-60 rounded-3xl flex items-center justify-center bg-gray-800"
        >
          <img src="/raccoon.png" alt="Raccoon Image" class="h-full py-5" />
        </button>
      </div>
    </main>
    <NavigationBar activeMenu="1" />
  </div>
</template>

<script setup>
import { ref } from 'vue';

const raccoons = ref(0);
const raccoons_per_sec = ref(0);

function tap() {
  raccoons.value++;
}
</script>
