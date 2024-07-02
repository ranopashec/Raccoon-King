<template>
  <footer class="fixed bottom-0 w-full h-16 bg-gray-950">
    <nav class="container mx-auto">
      <ul class="flex justify-center items-center py-2">
        <li class="px-4">
          <NuxtLink to="/"
            ><img
              :src="
                activeMenu === '1' ? '/navigationImgs/earn-active.png' : '/navigationImgs/earn.png'
              "
              class="object-contain h-12 w-12"
            />
          </NuxtLink>
        </li>
        <li class="px-4">
          <NuxtLink to="/cards"
            ><img
              :src="
                activeMenu === '2'
                  ? '/navigationImgs/cards-active.png'
                  : '/navigationImgs/cards.png'
              "
              class="object-contain h-12 w-12"
            />
          </NuxtLink>
        </li>
        <li class="px-4">
          <NuxtLink to="/settings"
            ><img
              :src="
                activeMenu === '3'
                  ? '/navigationImgs/settings-active.png'
                  : '/navigationImgs/settings.png'
              "
              class="object-contain h-12 w-12"
            />
          </NuxtLink>
        </li>
      </ul>
    </nav>
  </footer>
</template>

<script setup>
defineProps({
  activeMenu: String,
});
</script>
