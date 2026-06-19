<script setup>
import { useSlideContext } from '@slidev/client'
const { $frontmatter } = useSlideContext()
</script>

<template>
  <div class="slidev-layout dark-slide slide">
    <div class="shrink-0" style="margin-bottom: 0.5rem;">
      <div class="t-label" style="color: var(--orange); margin-bottom: 0.25rem;">{{ $frontmatter.label }}</div>
      <h1 class="t-h1">{{ $frontmatter.title }}</h1>
      <p class="t-subtitle" style="margin-top: 0.25rem;">{{ $frontmatter.desc }}</p>
    </div>
    <div class="flex gap-8 flex-1 items-center justify-center">
      <template v-if="$frontmatter.images">
        <div v-for="img in $frontmatter.images" :key="img.src" class="image-card text-center">
          <img :src="img.src" :alt="img.label" class="instrument-img" />
          <div class="t-body" style="color: var(--text-faint); margin-top: 0.75rem;">{{ img.label }}</div>
        </div>
      </template>
      <template v-else>
        <div v-for="stat in $frontmatter.stats" :key="stat.value" class="card-navy stat-card text-center">
          <div class="stat-value" style="color: var(--orange);">{{ stat.value }}</div>
          <div class="t-body" style="color: var(--text-faint); margin-top: 0.25rem;">{{ stat.label }}</div>
        </div>
      </template>
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
.stat-card {
  flex: 1;
  padding: 2rem 1.5rem;
}
.stat-value {
  font-size: 2rem;
  font-weight: 700;
}
.image-card {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.instrument-img {
  width: 340px;
  height: 240px;
  object-fit: cover;
  border-radius: 0.75rem;
  border: 2px solid rgba(255,255,255,0.08);
}
</style>
