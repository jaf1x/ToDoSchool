<script setup>
import { ref } from 'vue'
import { PAGE_PROGRESS } from './constants';
let bolly = ref(true)
</script>
<template>
  <a :href="`#${PAGE_PROGRESS}`" class="text-sm">
    <div v-if="bolly"  class="flex items-center gap-1">
      Day complete!
      <div class="h-3 w-3 rounded-full bg-green-500"></div>
    </div>
    <div v-else-if="!bolly" class="flex items-center gap-1">
      <div>Progress: <span class="font-mono">20%</span></div>
      <div class="h-3 w-3 rounded-full bg-red-500"></div>
    </div>
  </a>
</template>
