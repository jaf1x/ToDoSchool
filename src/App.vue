<script setup>
import Theheader from './/components/TheHeader.vue'
import TheNav from './components/TheNav.vue'
import TheTimeline from './pages/TheTimeline.vue'
import TheActivites from './pages/TheActivites.vue'
import TheProgress from './pages/TheProgress.vue'
import TheSettings from './pages/TheSettings.vue'
import { ref } from 'vue'
import { PAGE_TIMELINE, PAGE_ACTIVITES, PAGE_PROGRESS, PAGE_SETTINGS } from './components/constants'
const currentPage = ref(normalizePageHash())
function normalizePageHash() {
  const hash = window.location.hash.slice(1)

  if ([PAGE_ACTIVITES, PAGE_PROGRESS, PAGE_SETTINGS].includes(hash)) {
    return hash
  }
  window.location.hash = PAGE_TIMELINE
  return PAGE_TIMELINE
}
</script>

<template>
  <main class="absolute mt-24 ml-24 flex flex-grow flex-col">
    <TheTimeline v-show="currentPage === PAGE_TIMELINE" />
    <TheActivites v-show="currentPage === PAGE_ACTIVITES" />
    <TheProgress v-show="currentPage === PAGE_PROGRESS" />
    <TheSettings v-show="currentPage === PAGE_SETTINGS" />
  </main>
  <Theheader @go-to-timeline="currentPage = PAGE_TIMELINE"
    @go-to-progress="currentPage = PAGE_PROGRESS" />
  <TheNav :current-page="currentPage" @navigate="currentPage = $event" />
</template>
