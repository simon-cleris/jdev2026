<script setup>
import { useSlideContext } from '@slidev/client'
const { $frontmatter } = useSlideContext()
</script>

<template>
  <div class="slidev-layout dark-slide h-full flex flex-col items-center justify-center gap-8" style="padding: 0 var(--slide-px);">
    <div class="text-center">
      <div class="t-label mb-3" style="color: var(--indigo);">{{ $frontmatter.label }}</div>
      <h1 class="t-h1-xl mb-4">{{ $frontmatter.title }}</h1>
      <p class="t-body">{{ $frontmatter.desc }}</p>
    </div>
    <div class="flex gap-12 text-center">
      <div v-for="stat in $frontmatter.stats" :key="stat.value">
        <div class="text-3xl font-bold" style="color: var(--green);">{{ stat.value }}</div>
        <div class="t-body mt-1" style="color: var(--text-faint);">{{ stat.label }}</div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.dark-slide {
  background: var(--bg);
  color: var(--text);
  height: 100%;
  overflow: hidden;
}
</style>
