<script setup>
import { ref } from 'vue'
import {
  ClockIcon,
  ListBulletIcon,
  ChartBarIcon,
  AdjustmentsHorizontalIcon
} from '@heroicons/vue/24/outline'
import { PAGE_TIMELINE, PAGE_ACTIVITES, PAGE_PROGRESS, PAGE_SETTINGS } from './constants'
import NavItems from './NavItems.vue'

defineProps(['currentPage'])
const emit = defineEmits(['navigate'])

const navItems = {
  [PAGE_TIMELINE]: ClockIcon,
  [PAGE_ACTIVITES]: ListBulletIcon,
  [PAGE_PROGRESS]: ChartBarIcon,
  [PAGE_SETTINGS]: AdjustmentsHorizontalIcon
}
</script>
<template>
  <nav class="sticky right-0 z-10">
    <ul class="menu p-4 w-20 overflow-y-auto text-sm bg-base-100 border-r items-center">
      <NavItems
        class="mr-1"
        v-for="(icon, page) in navItems"
        :key="page"
        :href="`#${page}`"
        :class="{ 'bg-gray-200 pointer-events-none': page === currentPage }"
        @click="emit('navigate', page)"
      >
        <component :is="icon" class="h-10 w-6" /> {{ page }}
      </NavItems>
    </ul>
  </nav>
</template>
