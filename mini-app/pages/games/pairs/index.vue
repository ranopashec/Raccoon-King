<template>
  <div>
    <main class="bg-black text-white text-center mt-12">
      <h1 class="text-5xl">Find a Pair</h1>
      <section class="game-board">
        <Card v-for="(card, index) in cardList" :key="`card-${index}`" :myNumber="card" />
      </section>
    </main>
  </div>
</template>

<script setup>
import Card from './Card.vue';

const cardList = [];
for (let i = 0; i < 16; i++) {
  cardList.push(i);
}
</script>

<style>
.game-board {
  display: grid;
  grid-template-columns: 100px 100px 100px 100px;
  grid-template-rows: 100px 100px 100px 100px;
  grid-column-gap: 30px;
  grid-row-gap: 30px;
  justify-content: center;
}
</style>
