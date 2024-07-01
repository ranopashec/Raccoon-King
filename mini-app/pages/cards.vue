<template>
  <div>
    <h1 class="text-2xl font-bold mb-4">Internet Shop</h1>
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-2 gap-4">
      <CardItem
        v-for="card in cardArray"
        :key="card.name"
        :price="card.price"
        :output="card.output"
        :image="card.image"
        :name="card.name"
      />
    </div>
  </div>
</template>

<script setup>
import { inject } from 'vue';

const cardArray = [
  {
    name: 'Mining farm in university',
    price: 20,
    output: 2,
    image: '/FarmCard1.png',
  },
  {
    name: 'Create 10 acc to farm',
    price: 60,
    output: 6,
    image: '/FarmCard2.png',
  },
  {
    name: 'Pass assemembly',
    price: 120,
    output: 9,
    image: '/FarmCard3.png',
  },
];
</script>
