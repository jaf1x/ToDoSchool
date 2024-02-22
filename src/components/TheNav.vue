<script setup>
import { ClockIcon, ListBulletIcon, ChartBarIcon } from '@heroicons/vue/24/outline'
</script>
<template>
  <nav class="sticky right-0 z-10">
    <ul class="menu p-4 overflow-y-auto w-20 bg-base-100 border-r">
      <li class="flex-1">
        <a class="flex flex-col items-center p-2 capitalize h-20" href="#timeline">
          <ClockIcon class="h-6 w-6" /> timeline
        </a>
      </li>
      <li class="flex-1">
        <a class="flex flex-col items-center p-2 capitalize h-20" href="#activities">
          <ListBulletIcon class="h-6 w-6" /> activities
        </a>
      </li>
      <li class="flex-1">
        <a class="flex flex-col items-center p-2 capitalize h-20" href="#progress">
          <ChartBarIcon class="h-6 w-6" /> progress
        </a>
      </li>
    </ul>
  </nav>
</template>
