<script setup>
import { useSlideContext } from '@slidev/client'
const { $frontmatter } = useSlideContext()
</script>

<template>
  <div class="slidev-layout dark-slide slide">
    <div class="shrink-0" style="margin-bottom: 0.25rem;">
      <div class="t-label" style="color: var(--orange); margin-bottom: 0.25rem;">{{ $frontmatter.label }}</div>
      <h1 class="t-h1">{{ $frontmatter.title }}</h1>
    </div>
    <div class="projects-grid flex-1 min-h-0">
      <slot />
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

.projects-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0.875rem;
  align-content: start;
}
</style>
