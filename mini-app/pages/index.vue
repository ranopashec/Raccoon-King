<template>
  <main class="bg-gradient-to-tr font-sans min-h-screen py-4 px-4 from-yellow-950 to-purple-950">
    <MainHeader />
    <div class="flex flex-col items-center justify-center touch-pan-x gap-8 touch-pan-y mx-auto">
      <div class="flex flex-row w-full justify-center items-center gap-2 mt-8">
        <img src="/coin.png" alt="Coin Image" class="w-8 h-8" />
        <p class="text-3xl text-white font-semibold">{{ clicks }} RCN</p>
      </div>

      <button
        @click="incrementClicks"
        class="w-80 h-80 bg-black rounded-3xl flex flex-row items-center justify-center"
      >
        <img src="/raccoon.png" alt="Raccoon Image" class="w-40" />
      </button>
    </div>
  </main>
</template>

<script>
import { ref } from 'vue';
import MainHeader from '@/components/MainHeader.vue';

export default {
  name: 'ClickerGame',
  setup() {
    const clicks = ref(0);

    const incrementClicks = () => {
      clicks.value++;
    };

    return {
      clicks,
      incrementClicks,
    };
  },
};
</script>
