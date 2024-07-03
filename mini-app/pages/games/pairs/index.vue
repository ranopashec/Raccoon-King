<template>
  <div>
    <main class="bg-black text-white text-center mt-12">
      <h1 class="text-5xl">Find a Pair</h1>
      <section class="game-board">
        <Card
          v-for="(card, index) in cardList"
          :key="`card-${index}`"
          :value="card.value"
          :visible="card.visible"
          :position="card.position"
          :matched="card.matched"
          @selectCard="flipCard"
        />
      </section>
      <h2>{{ status }}</h2>
    </main>
  </div>
</template>

<script setup>
import Card from './Card.vue';
import { ref, watch } from 'vue';

const cardList = ref([]);
const userSelection = ref([]);

const status = computed(() => {
  if (remainingPairs.value === 0) {
    return 'You win!';
  } else {
    return `${remainingPairs.value} pairs left`;
  }
});

const remainingPairs = computed(() => {
  const RemainingCards = cardList.value.filter(card => card.matched === false).length;
  return RemainingCards / 2;
});

for (let i = 0; i < 16; i++) {
  cardList.value.push({
    value: 1,
    visible: false,
    position: i,
    matched: false,
  });
}

const flipCard = payload => {
  cardList.value[payload.position].visible = true;
  if (userSelection.value[0]) {
    userSelection.value[1] = payload;
  } else {
    userSelection.value[0] = payload;
  }
};

watch(
  userSelection,
  currentValue => {
    if (currentValue.length === 2) {
      const cardOne = currentValue[0];
      const cardTwo = currentValue[1];

      if (cardOne.value === cardTwo.value) {
        status.value = 'Matched!';

        cardList.value[cardOne.position].matched = true;
        cardList.value[cardTwo.position].matched = true;
      } else {
        status.value = 'Mismatched (';
        cardList.value[cardOne.position].visible = false;
        cardList.value[cardTwo.position].visible = false;
      }

      userSelection.value.length = 0;
      console.log(currentValue);
    }
  },
  { deep: true },
);
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
