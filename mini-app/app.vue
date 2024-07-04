<template>
  <NuxtPage />
</template>

<script setup>
import { provide, ref, reactive, onMounted, onBeforeUnmount } from 'vue';

const raccoonsPerSec = ref(0);
const raccoonsPerClick = ref(1);
const nickName = ref("Nickname");
const raccoons = ref(0);
const timer = ref();

onMounted(() => {
  nickName.value = window.Telegram.WebApp.initDataUnsafe.user.username;
});


onMounted(async () => {
  const storage = window.Telegram.WebApp.CloudStorage;
  const promise1 =  new Promise ((resolve) => {
    storage.getItem('raccoons', (error, value) => {
      if (error) {
        resolve (Number(0))
      } 
      if (value === null) {
        resolve (Number(0))
      }
      if (value == undefined) {
        resolve (Number(0))
      }
      resolve (Number(value))
    });
  })

  const value = await promise1;
  raccoons.value = value;
});

onMounted(() => {
  const storage = window.Telegram.WebApp.CloudStorage;
  timer.value = setInterval(() => {
    storage.setItem('raccoons', String(raccoons.value))
  }, 1000);
});
onBeforeUnmount(() => {
  timer.value = 0;
})

provide('raccoons', raccoons);
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


provide('raccoonsPerSec', raccoonsPerSec);
provide('raccoonsPerClick', raccoonsPerClick);
provide('farmingCards', farmingCards);
provide('nickName', nickName);
provide('userLevel', userLevel);
</script>
