<template>
  <div
    class="relative card"
    :class="{ flipped: props.visible }"
    @click="$emit('selectCard', { position, value })"
  >
    <div class="card-face front">
      <img :src="`/games/pairs/${value}.png`" />
    </div>
    <div class="card-face back">
      <!-- <img :src="`/games/pairs/back.png`" /> -->
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
  transition: transform 0.5s ease-in;
  backface-visibility: hidden;
  transform-style: preserve-3d;
}

.card.flipped {
  transform: rotateY(180deg);
}

.card-face {
  position: absolute;
  width: 100%;
  height: 100%;
}

.card-face.front {
  transform: rotateY(180deg);
}

.card-face.back {
  background-color: black; /* blue-500 color */
}
</style>
