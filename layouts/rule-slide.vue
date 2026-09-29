<script setup>
import { useSlideContext } from '@slidev/client'
const { $frontmatter } = useSlideContext()
</script>

<template>
  <div class="slidev-layout dark-slide slide">
    <div class="shrink-0 flex items-center gap-4" style="margin-bottom: 0.25rem;">
      <div v-if="$frontmatter.icon" class="rule-icon">
        <div :class="$frontmatter.icon" />
      </div>
      <div>
        <div class="t-label" style="color: var(--orange); margin-bottom: 0.25rem;">{{ $frontmatter.label }}</div>
        <h1 class="t-h1">{{ $frontmatter.title }}</h1>
        <p class="t-subtitle">{{ $frontmatter.desc }}</p>
      </div>
    </div>
    <div class="flex flex-col gap-3 flex-1 min-h-0 justify-center">
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

.rule-icon {
  flex-shrink: 0;
  width: 3.5rem;
  height: 3.5rem;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 0.75rem;
  font-size: 2rem;
  color: var(--orange);
  background: var(--orange-bg);
  border: 1px solid var(--orange-border);
}
</style>
