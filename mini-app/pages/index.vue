<template>
  <div class="bg-black">
    <main
      :class="classStyle">
      <MainHeader />
      <div class="flex flex-col items-center justify-center gap-8 mx-auto">
        <button
          @click="tap"
          class="my-10 w-60 h-60 rounded-3xl flex items-center justify-center bg-gray-800/50"
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
const classStyle = inject('classStyle');

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
  if (typeof userLevel.value.value !== 'number') {
    return '/raccoonImgs/0.png';
  }
  return `/raccoonImgs/${userLevel.value.value}.png`;
});
</script>
