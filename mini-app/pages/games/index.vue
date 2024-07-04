<script setup>
import Game from '~/components/games/pairs/Game.vue';
import Back from '~/components/Back.vue';
</script>

<template>
  <div class="bg-black text-white">
    <main
      class="font-sans min-h-screen touch-pan-x touch-pan-y py-4 px-4 bg-gradient-to-r from-0% via-20 via-50% to-100% from-purple-950/40 via-purple-950/20 to-purple-950/40"
    >
      <MainHeader />
      <div class="flex flex-col items-center justify-center gap-8 mx-auto">
        <Game />
      </div>
    </main>
    <Back />
  </div>
</template>
