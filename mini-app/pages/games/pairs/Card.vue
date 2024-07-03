<template>
  <div class="card">
    {{ myNumber }}
  </div>
</template>

<script setup>
defineProps({
  myNumber: {
    type: Number,
    required: true,
  },
});
</script>

<style>
.card {
  border: 5px solid #ccc;
}
</style>
