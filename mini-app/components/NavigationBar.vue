<template>
  <footer
    class="fixed bottom-0 w-full h-16 bg-gradient-to-r from-0% via-50% to-100% from-black via-gray-800 to-black"
  >
    <nav class="container mx-auto">
      <ul class="flex justify-center items-center py-2">
        <li class="px-4">
          <NuxtLink to="/"
            ><img
              :src="activeMenu === '1' ? '/earn-active.png' : '/earn.png'"
              class="object-contain h-12 w-12"
            />
          </NuxtLink>
        </li>
        <li class="px-4">
          <NuxtLink to="/cards"
            ><img
              :src="activeMenu === '2' ? '/cards-active.png' : '/cards.png'"
              class="object-contain h-12 w-12"
            />
          </NuxtLink>
        </li>
        <li class="px-4">
          <NuxtLink to="/settings"
            ><img
              :src="activeMenu === '3' ? '/settings-active.png' : '/settings.png'"
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
