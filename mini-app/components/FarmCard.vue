<template>
  <div
    class="bg-gray-800/50 rounded-lg w-full mx-auto"
    @click="$emit('someEvent', name, price, income)"
  >
    <div class="flex items-center justify-between p-2">
      <img class="h-20 w-20 object-cover mr-8" :src="image" alt="Card Image" />
      <b class="text-white text-m">{{ name }}</b>
    </div>
    <hr class="border-white" />
    <div class="bg-gray-950/60 flex justify-center rounded-b-lg">
      <span class="flex flex-row w-full justify-center items-center gap-1 py-2">
        <p class="text-base text-white font-semibold">{{ income }}</p>
        <img src="/coin.png" alt="Coin Image" class="w-4 h-4" />
        <p class="text-base text-white font-semibold">/ S</p>
      </span>
      <span class="flex flex-row w-full justify-center items-center gap-1 py-2">
        <p class="text-base text-white font-semibold">{{ price }}</p>
        <img src="/coin.png" alt="Coin Image" class="w-6 h-6" />
      </span>
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
