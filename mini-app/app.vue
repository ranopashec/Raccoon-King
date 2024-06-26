<template>
  <div class="flex flex-col items-center justify-center h-screen">
    <h1 class="text-4xl font-bold mb-4">Raccoon King</h1>
    <p class="text-xl mb-4">Clicks: {{ clicks }}</p>
    <button @click="incrementClicks">
      <img src="/raccoon.png" alt="Raccoon Image" class="w-64 h-auto" />
    </button>
  </div>
</template>

<script>
export default {
  name: "ClickerGame",
  data() {
    return {
      clicks: 0,
    };
  },
  methods: {
    incrementClicks() {
      this.clicks++;
    },
  },
};
</script>

<style>
@import "tailwindcss/base";
@import "tailwindcss/components";
@import "tailwindcss/utilities";
</style>
