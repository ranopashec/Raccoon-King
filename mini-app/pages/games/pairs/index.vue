<template>
  <div class="bg-black text-white text-center h-screen py-10">
    <h1 class="text-5xl py-10">Find a Pair</h1>
    <transition-group name="shuffle-card" tag="section" class="game-board">
      <Card
        v-for="card in cardList"
        :key="`${card.value}-${card.variant}`"
        :value="card.value"
        :visible="card.visible"
        :position="card.position"
        :matched="card.matched"
        @selectCard="flipCard"
      />
    </transition-group>
    <h2>{{ status }}</h2>
    <button @click="restart">Reset</button>
  </div>
</template>

<script setup>
import Card from '~/components/games/pairs/Card.vue';
import { ref, watch } from 'vue';

const cardList = ref([]);
const userSelection = ref([]);
const cardItems = [1, 2, 3, 4, 5, 6, 7, 8];

cardItems.forEach(item => {
  cardList.value.push({
    value: item,
    variant: 1,
    visible: false,
    position: null,
    matched: false,
  });
  cardList.value.push({
    value: item,
    variant: 2,
    visible: false,
    position: null,
    matched: false,
  });
});

cardList.value = cardList.value.map((card, index) => {
  return {
    ...card,
    position: index,
  };
});

const remainingPairs = computed(() => {
  const RemainingCards = cardList.value.filter(card => card.matched === false).length;
  return RemainingCards / 2;
});

const status = computed(() => {
  if (remainingPairs.value === 0) {
    return 'You win!';
  } else {
    return `${remainingPairs.value} pairs left`;
  }
});

watch(
  userSelection,
  currentValue => {
    if (currentValue.length === 2) {
      const cardOne = currentValue[0];
      const cardTwo = currentValue[1];

      if (cardOne.value === cardTwo.value && cardOne.position !== cardTwo.position) {
        cardList.value[cardOne.position].matched = true;
        cardList.value[cardTwo.position].matched = true;
      } else {
        setTimeout(() => {
          if (!cardList.value[cardOne.position].matched) {
            cardList.value[cardOne.position].visible = false;
          }
          if (!cardList.value[cardTwo.position].matched) {
            cardList.value[cardTwo.position].visible = false;
          }
        }, 500);
      }
      userSelection.value.length = 0;
      console.log(currentValue);
    } else if (currentValue.length > 2) {
    }
  },
  { deep: true },
);

const flipCard = payload => {
  cardList.value[payload.position].visible = true;
  if (userSelection.value[0]) {
    userSelection.value[1] = payload;
  } else {
    userSelection.value[0] = payload;
  }
};

const restart = () => {
  for (let i = cardList.value.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [cardList.value[i], cardList.value[j]] = [cardList.value[j], cardList.value[i]];
  }
  cardList.value = cardList.value.map((card, index) => {
    return {
      ...card,
      matched: false,
      position: index,
      visible: false,
    };
  });
};
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

.shuffle-card-move {
  transition: transform 0.8s ease-in;
}
</style>
