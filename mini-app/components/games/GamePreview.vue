<template>
  <div class="rounded-lg w-40 mx-auto relative bg-gray-950 mb-24">
    <NuxtLink :to="link">
      <div class="flex items-center justify-between p-2">
        <img class="h-40 w-full object-cover mx-auto" :src="image" alt="Card Image" />
      </div>
      <div class="flex justify-center rounded-xl h-10">
        <b class="text-gray-400 text-m my-auto">{{ name }}</b>
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
