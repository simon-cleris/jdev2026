<script setup>
import { useSlideContext } from '@slidev/client'
import ApproachRules from '../components/ApproachRules.vue'
const { $frontmatter } = useSlideContext()
</script>

<template>
  <div class="slidev-layout dark-slide slide" style="gap: 0.75rem; padding-top: 1rem;">
    <div class="shrink-0 card-navy text-center">
      <div class="t-label mb-1" style="color: var(--orange);">{{ $frontmatter.label }}</div>
      <div class="text-sm font-bold leading-snug" style="color: var(--text-strong);">{{ $frontmatter.tagline }}</div>
      <div class="t-body-sm mt-1">{{ $frontmatter.paradox }}</div>
    </div>
    <div class="flex gap-6 flex-1 min-h-0 overflow-hidden">
      <ApproachRules
        :items="$frontmatter.tech"
        variant="orange"
        title="Approche technique"
        :click-offset="1"
      />
      <ApproachRules
        :items="$frontmatter.guards"
        variant="navy"
        title="Garde-fous"
        :click-offset="6"
      />
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
