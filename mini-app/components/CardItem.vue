<template>
  <li>
    <div class="card bg-white shadow-lg rounded-lg overflow-hidden">
      <img :src="image" :alt="name" class="w-full h-48 object-cover" />
      <div class="p-6">
        <h2 class="text-xl font-bold mb-2">{{ name }}</h2>
        <h3 class="text-gray-700 mb-4"> {{ price }} RCN </h3>
        <h3 class="text-gray-700"> + {{ output }} RCN/sec </h3>
      </div>
    </div>
    </li>
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
    output: {
      type: Number,
      required: true,
    },
  })
  </script>