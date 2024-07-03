<template>
  <div class="rounded-lg w-3/4 mx-auto relative bg-gray-950 mb-24">
    <NuxtLink :to="link">
      <div class="flex items-center justify-between p-2">
        <img class="h-20 w-20 object-fit mx-auto" :src="image" alt="Card Image" />
        <img class="h-20 w-20 object-fit mx-auto" :src="image" alt="Card Image" />
      </div>
      <hr class="border-gray-400 border-2 rounded-none" />
      <div class="flex justify-center rounded-b-lg h-10">
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
