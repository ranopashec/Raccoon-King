<template>
  <div class="relative card" @click="$emit('selectCard', { position, value })">
    <div class="card-face rounded-xl">
      <img
        v-if="visible"
        class="rounded-xl border-solid border-purple-500/50 border-4"
        :src="`/games/pairs/${value}.png`"
      />
      <img
        v-else
        class="rounded-xl border-solid border-pink-500/50 border-4"
        :src="`/games/pairs/card.png`"
      />
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  matched: {
    type: Boolean,
    default: false,
  },
  position: {
    type: Number,
    required: false,
  },
  value: {
    type: Number,
    required: true,
  },
  visible: {
    type: Boolean,
    required: true,
  },
});
</script>

<style scoped>
.card {
  position: relative;
}

.card-face {
  position: absolute;
  background-color: #fdf7df;

  width: 100%;
  height: 100%;
}
</style>
