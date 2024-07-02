<template>
  <div>
    <main>
      <h1 class="text-2xl font-bold mb-4">Internet Shop</h1>
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-2 gap-4">
        <CardItem
          v-for="card in cardArray"
          :key="card.name"
          :price="card.price"
          :output="card.output"
          :image="card.image"
          :name="card.name"
          @some-event="buy"
        />
      </div>
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-2 gap-4">
        <CardItem1
          v-for="card in cardArray1"
          :key="card.name"
          :price="card.price"
          :output="card.output"
          :image="card.image"
          :name="card.name"
          @some-event="buy1"
        />
      </div>
    </main>
    <NavigationBar activeMenu="2" />
  </div>
</template>

<script setup>
import { inject } from 'vue';

const cardArray = inject('cardArray');
const cardArray1 = inject('cardArray1');

const raccoons = inject('raccoons');
const raccoons_per_sec = inject('raccoons_per_sec');
const raccoons_per_clck = inject('raccoons_per_clck');

function buy(name, price, output) {
  if (raccoons.value >= price) {
    raccoons.value -= price;
    raccoons_per_sec.value += output;
    let foundCard = cardArray.find((card) => card.name === name);
    console.log(`You buy ${foundCard.name}!`)
    foundCard.price = foundCard.price * 6
    foundCard.output = foundCard.output * 2
    console.log(foundCard.price)
    console.log(foundCard.output)
  }
}

function buy1(name, price, output) {
  if (raccoons.value >= price) {
    raccoons.value -= price;
    raccoons_per_clck.value += output;
    let foundCard = cardArray.find((card) => card.name === name);
    console.log(`You buy ${foundCard.name}!`)
    foundCard.price = foundCard.price * 6
    foundCard.output = foundCard.output * 2
    console.log(foundCard.price)
    console.log(foundCard.output)
  }
}
</script>
