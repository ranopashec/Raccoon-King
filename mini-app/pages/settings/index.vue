<template>
  <main
    class="bg-black text-white w-screen h-screen flex flex-col jastify-center items-center text-center"
  >
    <h1>settings</h1>
    <button @click="resetAll">Reset All</button>
    <button @click="changeTheme">Reset Farming Cards</button>
    <NavigationBar activeMenu="3" />
  </main>
</template>

<script setup>
import { inject } from 'vue';

const raccoons = inject('raccoons');
const raccoonsPerSec = inject('raccoonsPerSec');
const farmingCards = inject('farmingCards');
const theme2 = inject('theme2');
function resetAll() {
  raccoons.value = 0;
  raccoonsPerSec.value = 0;
  farmingCards.value = [
    {
      name: 'Mining farm in university',
      price: 20,
      income: 2,
      image: '/farmCardsImgs/1.png',
    },
    {
      name: 'Multiaccount',
      price: 60,
      income: 6,
      image: '/farmCardsImgs/2.png',
    },
    {
      name: 'Assemembly classes',
      price: 120,
      income: 9,
      image: '/farmCardsImgs/3.png',
    },
    {
      name: 'Trash recycling',
      price: 20,
      income: 2,
      image: '/farmCardsImgs/4.png',
    },
    {
      name: 'Janchik',
      price: 60,
      income: 6,
      image: '/farmCardsImgs/5.png',
    },
    {
      name: 'subbotnik',
      price: 120,
      income: 9,
      image: '/farmCardsImgs/6.png',
    },
  ];
}

function changeTheme() {
  theme2.value = !theme2.value;
}
</script>
