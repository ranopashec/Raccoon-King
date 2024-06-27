<template>
  <main
    class="touch-pan-x touch-pan-y bg-gradient-to-tr font-sans min-h-screen py-4 px-4 from-yellow-950 to-purple-950"
  >
    <MainHeader />
    <div
      class="flex flex-col items-center justify-center  gap-8 mx-auto"
    >
      <div class="flex flex-row w-full justify-center items-center gap-2 mt-8">
        <img src="/coin.png" alt="Coin Image" class="w-8 h-8" />
        <p class="text-3xl text-white font-semibold">{{ raccoons }} RCN</p>
      </div>

      <button
        @click="tap"
        class="w-80 h-80 bg-black rounded-3xl flex flex-row items-center justify-center"
      >
        <img src="/raccoon.png" alt="Raccoon Image" class="w-40" />
      </button>
    </div>
  </main>
</template>

<script setup>
import MainHeader from "~/components/MainHeader.vue";
import { ref } from "vue";
const raccoons = ref(0);
const raccoons_per_sec = ref(0);

function tap() {
  raccoons.value++;
}
</script>
