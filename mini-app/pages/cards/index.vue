<template>
  <div class="bg-black">
    <MainHeader />
    <main>
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-2 gap-4">
        <FarmCard
          v-for="card in cardArrayFarm"
          :key="card.name"
          :price="card.price"
          :output="card.output"
          :image="card.image"
          :name="card.name"
          @some-event="buyFarm"
        />
      </div>
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-2 gap-4">
        <ClickCard
          v-for="card in cardArrayClick"
          :key="card.name"
          :price="card.price"
          :output="card.output"
          :image="card.image"
          :name="card.name"
          @some-event="buyClick"
        />
      </div>
    </main>
    <NavigationBar activeMenu="2" />
  </div>
</template>

<script setup>
import { inject } from 'vue';

const cardArrayFarm = inject('cardArrayFarm');
const cardArrayClick = inject('cardArrayClick');

const raccoons = inject('raccoons');
const raccoons_per_sec = inject('raccoons_per_sec');
const raccoons_per_clck = inject('raccoons_per_clck');

function buyFarm(name, price, output) {
  if (raccoons.value >= price) {
    raccoons.value -= price;
    raccoons_per_sec.value += output;
    let foundCard = cardArrayFarm.find(card => card.name === name);
    console.log(`You buy ${foundCard.name}!`);
    foundCard.price = foundCard.price * 6;
    foundCard.output = foundCard.output * 2;
    console.log(foundCard.price);
    console.log(foundCard.output);
  }
}

function buyClick(name, price, output) {
  if (raccoons.value >= price) {
    raccoons.value -= price;
    raccoons_per_clck.value += output;
    let foundCard = cardArrayClick.find(card => card.name === name);
    console.log(`You buy ${foundCard.name}!`);
    foundCard.price = foundCard.price * 6;
    foundCard.output = foundCard.output * 2;
    console.log(foundCard.price);
    console.log(foundCard.output);
  }
}
</script>
