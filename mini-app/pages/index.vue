<template>
  <div>
    <main
      class="font-sans min-h-screen touch-pan-x touch-pan-y py-4 px-4 bg-gradient-to-r from-0% via-50% to-100% from-black via-purple-950 to-black"
    >
      <MainHeader />
      <div class="flex flex-col items-center justify-center gap-8 mx-auto">
        <button
          @click="tap"
          class="my-10 w-60 h-60 rounded-3xl flex items-center justify-center bg-gradient-to-r from-0% via-50% to-100% from-black via-gray-800 to-black"
        >
          <img :src="raccoonImg" alt="Raccoon Image" class="h-full py-5" />
        </button>
      </div>
    </main>
    <NavigationBar activeMenu="1" />
  </div>
</template>

<script setup>
import { ref, inject, computed, onMounted, onBeforeUnmount } from 'vue';

const raccoonsPerSec = inject('raccoonsPerSec');
const raccoons = inject('raccoons');
const raccoonsPerClick = inject('raccoonsPerClick');

const timer = ref();

function tap() {
  raccoons.value += raccoonsPerClick.value;
}

function farm() {
  raccoons.value += raccoonsPerSec.value;
}

onMounted(() => {
  timer.value = setInterval(() => {
    farm();
  }, 1000);
});

onBeforeUnmount(() => {
  timer.value = null;
});

const raccoonImg = computed(function () {
  let userLevel = inject('userLevel');
  return `/raccoonImgs/${userLevel.value.value}.png`;
});
</script>
