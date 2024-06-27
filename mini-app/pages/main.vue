<template>
  <div
    class="font-inter flex flex-col items-center justify-center w-screen h-screen app-container touch-pan-x touch-pan-y mx-auto max-w-screen-md"
  >
    <div class="grid grid-cols-2 gap-4 mb-5 w-full px-4">
      <div
        class="flex flex-col items-center justify-center p-2 bg-green-400 rounded-lg"
      >
        <span class="text-xl font-medium">Nickname</span>
        <span>progress lvl</span>
      </div>

      <div
        class="flex flex-col items-center justify-center p-2 w-full rounded-lg bg-purple-600"
      >
        <div>RCN/s</div>
        <div>0</div>
      </div>
    </div>

    <p class="text-xl gap-10 mb-10 mt-5">{{ clicks }} RCN</p>

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
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap");
</style>
