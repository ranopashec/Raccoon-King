<script setup>
import GamePreview from '~/components/games/GamePreview.vue';
</script>

<template>
  <div class="bg-gray-800/50 mt-4 w-full py-4 rounded-lg flex flex-col items-center justify-center">
    <h1 class="text-white mb-10 text-3xl">Games</h1>
    <GamePreview name="FIND A PAIR" image="/games/pairs/1.png" link="/games" />
  </div>
</template>
