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
    <div class="img-zone">
      <div class="img-frame">
        <img src="/assets/influence.png" alt="Influence diagram" class="influence-img" />
      </div>
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
.img-zone {
  flex: 1;
  min-height: 0;
  display: flex;
  justify-content: center;
  padding-bottom: 7rem;
}
.img-frame {
  height: 100%;
  background: white;
  border-radius: 0.75rem;
  padding: 0.5rem;
  box-shadow: 0 6px 24px rgba(0, 0, 0, 0.3);
}
.influence-img {
  display: block;
  height: 100%;
  width: auto;
  border-radius: 0.5rem;
}
</style>
