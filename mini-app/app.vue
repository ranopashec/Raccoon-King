<template>
  <NuxtPage />
</template>

<script setup>
import { provide, ref } from 'vue';
const raccoons = ref(1000);
const raccoons_per_sec = ref(0);
const raccoons_per_clck = ref(1);
const nameF1 = ref('Mining farm in university');
const priceF1 = ref(20);
const outputF1 = ref(20);
const imageF1 = ref('/FarmCard1.png');

const cardArrayFarm = reactive([
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
]);

const cardArrayClick = reactive([
  {
    name: 'Trash recycling',
    price: 20,
    output: 2,
    image: '/LootCard1.png',
  },
  {
    name: 'janchik',
    price: 60,
    output: 6,
    image: '/LootCard2.png',
  },
  {
    name: 'subbotnik',
    price: 120,
    output: 9,
    image: '/LootCard3.png',
  },
]);

provide('raccoons', raccoons);
provide('raccoons_per_sec', raccoons_per_sec);
provide('raccoons_per_clck', raccoons_per_clck);
provide('cardArrayFarm', cardArrayFarm);
provide('cardArrayClick', cardArrayClick);
</script>
