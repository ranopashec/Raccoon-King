<template>
  <div class="flex flex-col items-center justify-center h-screen">
    <div class="grid grid-cols-2 gap-4">
      <div class="flex flex-col items-center justify-center">
        <div>nickname</div>
        <div>progress lvl</div>
      </div>

      <div class="flex flex-col items-center justify-center">
        <div>RCN/s</div>
        <div>0</div>
      </div>
    </div>
    <p class="text-xl mb-4">Clicks: {{ clicks }}</p>

    <button @click="incrementClicks">
      <img src="/raccoon.png" alt="Raccoon Image" class="w-64 h-auto" />
    </button>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  name: "ClickerGame",
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

<style scoped>
.grid {
  max-width: 800px;
  margin: 0 auto;
}
</style>
