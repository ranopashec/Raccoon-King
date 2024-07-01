<template>
  <div>
    <main
      class="font-sans min-h-screen touch-pan-x touch-pan-y py-4 px-4 bg-gradient-to-r from-0% via-50% to-100% from-black via-purple-950 to-black"
    >
      <MainHeader
        :nick-name="nickName"
        :user-status="userStatus"
        :level-num="levelNum"
        :speed-rcn="raccoons_per_sec"
      />
      <div class="flex flex-col items-center justify-center gap-8 mx-auto">
        <div class="flex flex-row w-full justify-center items-center gap-2 mt-8">
          <img src="/coin.png" alt="Coin Image" class="w-8 h-8" />
          <p class="text-3xl text-white font-semibold">{{ raccoons }} RCN</p>
        </div>

        <button
          @click="tap"
          class="w-60 h-60 rounded-3xl flex items-center justify-center bg-gray-800"
        >
          <img :src="avatarPng" alt="Raccoon Image" class="h-full py-5" />
        </button>
      </div>
    </main>
    <NavigationBar activeMenu="1" />
  </div>
</template>

<script setup>
import { ref, inject, computed, onMounted, onBeforeUnmount } from 'vue';

const raccoons_per_sec = inject('raccoons_per_sec');
const raccoons = inject('raccoons');
const raccoons_per_clck = inject('raccoons_per_clck');

const timer = ref();

function tap() {
  raccoons.value += raccoons_per_clck.value;
}

function farm() {
  raccoons.value += raccoons_per_sec.value;
}

onMounted(() => {
  timer.value = setInterval(() => {
    farm();
  }, 1000);
});

onBeforeUnmount(() => {
  timer.value = null;
});

const avatarPng = computed(function () {
  if (raccoons.value < 30) {
    return '/1 bomj.png';
  } else if (raccoons.value < 60) {
    return '/2 rookie.png';
  } else if (raccoons.value < 90) {
    return '/3 nobleman.png';
  } else if (raccoons.value < 100) {
    return '/4 king.png';
  } else {
    return '/5 $igma.png';
  }
});

const nickName = 'Nickname';

const userStatus = computed(function () {
  if (raccoons.value < 30) {
    return 'Bomj';
  } else if (raccoons.value < 60) {
    return 'Rookie';
  } else if (raccoons.value < 90) {
    return 'Nobleman';
  } else if (raccoons.value < 100) {
    return 'King';
  } else {
    return '$igma';
  }
});

const levelNum = computed(function () {
  if (raccoons.value < 30) {
    return 1;
  } else if (raccoons.value < 60) {
    return 2;
  } else if (raccoons.value < 90) {
    return 3;
  } else if (raccoons.value < 100) {
    return 4;
  } else {
    return 5;
  }
});
</script>
