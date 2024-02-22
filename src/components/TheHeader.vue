<script setup>
import { ref } from 'vue'
let bolly = ref(true)
</script>
<template>
  <header class="sticky top-0 z-20 flex items-center justify-between border-b bg-white p-3">
    <a href="#">
      <img src="../assets//logo.png" alt="Logo" class="h-9" />
    </a>
    <a href="#" class="text-sm">
      <div v-if="bolly" @click="bolly = false" class="flex items-center gap-1">
        Day complete!
        <div class="h-3 w-3 rounded-full bg-green-500"></div>
        <CheckCircleIcon class="h-7 text-green-500" />
      </div>
      <div v-else-if="!bolly" @click="bolly = true" class="flex items-center gap-1">
        <div>Progress: <span class="font-mono">20%</span></div>
        <div class="h-3 w-3 rounded-full bg-red-500"></div>
      </div>
    </a>
  </header>
</template>
