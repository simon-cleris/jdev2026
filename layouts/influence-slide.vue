<script setup>
import { useSlideContext } from '@slidev/client'
const { $frontmatter } = useSlideContext()
</script>

<template>
  <div class="slidev-layout dark-slide slide" style="padding-top: 1rem;">
    <div class="shrink-0">
      <div class="t-label" style="color: var(--orange); margin-bottom: 0.25rem;">{{ $frontmatter.label }}</div>
      <h1 class="t-h1">{{ $frontmatter.title }}</h1>
    </div>
    <div class="flex flex-1 min-h-0 items-center justify-center" style="padding-bottom: 4rem;">
      <img src="/assets/influence.png" alt="Influence diagram" class="influence-img" />
    </div>
    <slot />
  </div>
</template>

<style scoped>
.dark-slide {
  background: var(--bg);
  color: var(--text);
  height: 100%;
  overflow: hidden;
}
.influence-img {
  max-height: 100%;
  max-width: 100%;
  object-fit: contain;
}
</style>
