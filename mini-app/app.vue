<template>
  <NuxtPage />
</template>

<script setup>
import { provide, ref, reactive, onMounted, onBeforeUnmount } from 'vue';

const raccoonsPerSec = ref(0);
const raccoonsPerClick = ref(1);
const nickName = ref('Nickname');
const raccoons = ref(0);
const timer = ref();
const theme2 = ref(false);

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

onMounted(() => {
  nickName.value = window.Telegram.WebApp.initDataUnsafe.user.username;
});

onMounted(async () => {
  const storage = window.Telegram.WebApp.CloudStorage;
  const promise1 = new Promise(resolve => {
    storage.getItem('raccoons', (error, value) => {
      if (value === null || value === undefined || error) {
        resolve(Number(0));
      }
      resolve(Number(value));
    });
  });
  const value1 = await promise1;
  raccoons.value = value1;

  const promise2 = new Promise(resolve => {
    storage.getItem('raccoonsPerSec', (error, value) => {
      if (value === null || value === undefined || error) {
        resolve(Number(0));
      }
      resolve(Number(value));
    });
  });
  const value2 = await promise2;
  raccoonsPerSec.value = value2;
});

onMounted(() => {
  const storage = window.Telegram.WebApp.CloudStorage;
  timer.value = setInterval(() => {
    storage.setItem('raccoons', String(raccoons.value));
    storage.setItem('raccoonsPerSec', String(raccoonsPerSec.value));
  }, 1000);
});
onBeforeUnmount(() => {
  timer.value = 0;
});

provide('raccoons', raccoons);
const userLevel = ref(0);

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

const classStyle = computed(function () {
  // if (theme2) {
  //   return "font-sans min-h-screen touch-pan-x touch-pan-y py-4 px-4 bg-gradient-to-r from-0% via-20 via-50% to-100% from-green-950/40 via-green-950/20 to-green-950/40";
  // } else {
  return 'font-sans min-h-screen touch-pan-x touch-pan-y py-4 px-4 bg-gradient-to-r from-0% via-20 via-50% to-100% from-purple-950/40 via-purple-950/20 to-purple-950/40';
  // }
});

provide('raccoonsPerSec', raccoonsPerSec);
provide('raccoonsPerClick', raccoonsPerClick);
provide('farmingCards', farmingCards);
provide('nickName', nickName);
provide('userLevel', userLevel);
provide('theme2', theme2);
provide('classStyle', classStyle);
</script>
