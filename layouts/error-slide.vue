<script setup>
import { useSlideContext } from '@slidev/client'
const { $frontmatter } = useSlideContext()
</script>

<template>
  <div class="slidev-layout dark-slide slide" style="gap: 1rem;">
    <div class="shrink-0">
      <div class="t-label" style="color: var(--text-faint);">{{ $frontmatter.context }}</div>
      <h1 class="t-h1" style="margin-top: 0.25rem;">{{ $frontmatter.title }}</h1>
    </div>
    <div class="cards-container flex flex-col flex-1 min-h-0 overflow-hidden">
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

.cards-container {
  gap: 0.4rem;
}

.cards-container :deep(> *) {
  flex: 1;
  min-height: 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
</style>
