<template>
  <header class="touch-pan-y touch-pan-x grid grid-cols-2 gap-4 w-full px-4">
    <div class="flex flex-col items-center justify-center gap-2 rounded-lg">
      <div class="flex flex-row justify-between items-center w-full">
        <img src="/avatar.png" alt="Avatar Image" class="w-6 h-6" />
        <span class="text-md font-medium text-white">Nickname</span>
      </div>
      <div class="flex flex-col gap-1 w-full">
        <div class="w-full flex justify-between">
          <span class="text-xs font-medium text-white">Bomj</span>
          <span class="text-xs font-medium text-white">lvl 1/5</span>
        </div>
        <div class="w-full rounded-full bg-white/65 h-6">
          <div
            class="w-1/2 h-6 rounded-full bg-gradient-to-r from-purple-500 to-pink-400"
          ></div>
        </div>
      </div>
    </div>

    <div
      class="flex flex-col items-center justify-center p-2 w-full rounded-lg bg-gradient-to-r from-20% via-50% to-80% from-black via-yellow-900 to-black"
    >
      <span class="text-xl font-medium text-white">RCN/sec</span>
      <span class="text-2xl font-medium text-white">0</span>
    </div>
  </header>
</template>

<script>
export default {
  head() {
    return {
      meta: [
        {
          name: 'viewport',
          content: 'width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no'
        }
      ]
    }
  }
}
</script>
