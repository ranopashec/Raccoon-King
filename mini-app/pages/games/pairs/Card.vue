<template>
  <div class="border-4 border-white border-solid relative" @click="$emit('selectCard', position)">
    <div v-if="visible" class="bg-red-500 w-full h-full absolute">{{ value }}</div>
    <div v-else class="bg-blue-500 w-full h-full absolute">Back</div>
  </div>
</template>

<script setup>
defineProps({
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
