<script setup>
import { useSlideContext } from '@slidev/client'
const { $frontmatter } = useSlideContext()
</script>

<template>
  <div class="slidev-layout dark-slide slide">
    <div class="shrink-0" style="margin-bottom: 0.5rem;">
      <div class="t-label" style="color: var(--green); margin-bottom: 0.25rem;">{{ $frontmatter.label }}</div>
      <h1 class="t-h1">{{ $frontmatter.title }}</h1>
      <p class="t-subtitle" style="margin-top: 0.25rem;">{{ $frontmatter.desc }}</p>
    </div>
    <div class="flex flex-col gap-3 flex-1 min-h-0 justify-center" style="padding-top: 0.75rem;">
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
</style>
