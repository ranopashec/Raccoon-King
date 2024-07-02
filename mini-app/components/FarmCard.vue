<template>
  <div class="bg-gray-900" @click="$emit('someEvent', name, price, income)">
    <img class="h-40 w-full object-cover rounded-t-lg" :src="image" alt="Card Image" />
    <div class="p-4">
      <h3 class="text-lg font-bold mb-2">{{ name }}</h3>
      <p class="text-gray-700">Price: {{ price }}</p>
      <p class="text-gray-700">Outcome: {{ income }}</p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  name: {
    type: String,
    required: true,
  },
  price: {
    type: Number,
    required: true,
  },
  image: {
    type: String,
    required: true,
  },
  income: {
    type: Number,
    required: true,
  },
});
</script>
