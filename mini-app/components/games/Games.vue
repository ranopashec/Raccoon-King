<script setup>
import GamePreview from '~/components/games/GamePreview.vue';
</script>

<template>
  <div class="bg-gray-800/50 mt-4 w-full py-4 rounded-lg flex flex-col items-center justify-center">
    <h1 class="text-white mb-4 mt-2 text-3xl">Games</h1>
    <GamePreview name="FIND A PAIR" image="/games/pairs/cover.png" link="/games" />
  </div>
</template>
