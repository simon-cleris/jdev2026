<script setup>
import { useSlideContext } from '@slidev/client'
const { $frontmatter } = useSlideContext()
</script>

<template>
  <div class="slidev-layout dark-slide section">
    <div class="section-number">{{ $frontmatter.number }}</div>
    <div class="section-body">
      <div class="t-label" style="color: var(--orange);">Partie {{ Number($frontmatter.number) }} / 6</div>
      <h1 class="section-title">{{ $frontmatter.title }}</h1>
      <p v-if="$frontmatter.desc" class="section-desc">{{ $frontmatter.desc }}</p>
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
.section {
  display: flex;
  align-items: center;
  gap: 3rem;
  padding: 0 var(--slide-px);
}
.section-number {
  font-family: monospace;
  font-size: 9rem;
  font-weight: 700;
  line-height: 1;
  color: var(--orange);
  opacity: 0.85;
}
.section-body {
  border-left: 3px solid var(--orange);
  padding-left: 2rem;
}
.section-title {
  font-size: 2.5rem;
  font-weight: 700;
  color: var(--text-strong);
  margin: 0.5rem 0;
}
.section-desc {
  font-size: 1.125rem;
  color: var(--text-muted);
}
</style>
