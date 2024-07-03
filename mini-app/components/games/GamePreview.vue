<template>
  <div class="bg-gray-800/50 rounded-lg w-3/4 mx-auto relative">
    <NuxtLink :to="link">
      <div class="flex items-center justify-between p-2">
        <img class="h-20 w-20 object-cover mr-8" :src="image" alt="Card Image" />
      </div>
      <hr class="border-white" />
      <div class="bg-gray-950/60 flex justify-center rounded-b-lg">
        <b class="text-white text-m">{{ name }}</b>
      </div>
    </NuxtLink>
  </div>
</template>

<script setup>
defineProps({
  name: {
    type: String,
    required: true,
  },
  image: {
    type: String,
    required: true,
  },
  link: {
    type: String,
    required: true,
  },
});
</script>
