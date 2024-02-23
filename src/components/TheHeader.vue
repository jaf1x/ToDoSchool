<script setup>
import { ref } from 'vue'
import TheLogo from './TheLogo.vue'
import TheProgressHeader from './TheProgressHeader.vue'

const emit = defineEmits(['goToTimeline', 'goToProgress'])
</script>
<template>
  <header class="sticky top-0 z-20 flex items-center justify-between border-b bg-white p-3">
    <TheLogo @click="emit('goToTimeline')" />
    <TheProgressHeader  @click="emit('goToProgress')"/>
  </header>
</template>
