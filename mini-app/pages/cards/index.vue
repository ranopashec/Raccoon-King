<template>
  <div class="bg-black">
    <main
      class="font-sans min-h-screen touch-pan-x touch-pan-y py-4 px-4 bg-gradient-to-r from-0% via-20 via-50% to-100% from-purple-950/40 via-purple-950/20 to-purple-950/40"
    >
      <MainHeader />

      <div>
        <div class="grid grid-cols-1 gap-4 py-8 mb-10">
          <FarmCard
            v-for="card in farmingCards"
            :key="card.name"
            :price="card.price"
            :income="card.income"
            :image="card.image"
            :name="card.name"
            @some-event="buyFarmCard"
          />
        </div>
      </div>
    </main>
    <NavigationBar activeMenu="2" />
  </div>
</template>

<script setup>
import { inject } from 'vue';

const farmingCards = inject('farmingCards');
const raccoons = inject('raccoons');
const raccoonsPerSec = inject('raccoonsPerSec');

function buyFarmCard(name, price, income) {
  if (raccoons.value >= price) {
    raccoons.value -= price;
    raccoonsPerSec.value += income;
    let foundCard = farmingCards.find(card => card.name === name);
    console.log(`You buy ${foundCard.name}!`);
    foundCard.price = foundCard.price * 6;
    foundCard.income = foundCard.income * 2;
    console.log(foundCard.price);
    console.log(foundCard.income);
  }
}
</script>
