<template>
  <NuxtPage />
</template>

<script setup>
import { provide, ref } from 'vue';
const raccoons = ref(1000);
const raccoonsPerSec = ref(0);
const raccoonsPerClick = ref(1);
const nickName = ref('nickname');

onMounted(() => {
  nickName.value = window.Telegram.WebApp.initDataUnsafe.user.username;
});

const userLevel = ref(0);

const farmingCards = reactive([
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
]);

userLevel.value = computed(function () {
  if (raccoonsPerSec.value < 1000) {
    return 0;
  } else if (raccoonsPerSec.value < 10000) {
    return 1;
  } else if (raccoonsPerSec.value < 100000) {
    return 2;
  } else if (raccoonsPerSec.value < 1000000) {
    return 3;
  } else {
    return 4;
  }
});

provide('raccoons', raccoons);
provide('raccoonsPerSec', raccoonsPerSec);
provide('raccoonsPerClick', raccoonsPerClick);
provide('farmingCards', farmingCards);
provide('nickName', nickName);
provide('userLevel', userLevel);
</script>
