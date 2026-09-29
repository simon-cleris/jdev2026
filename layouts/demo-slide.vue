<script setup>
import { useSlideContext } from '@slidev/client'
const { $frontmatter } = useSlideContext()
const total = 7
</script>

<template>
  <div class="slidev-layout dark-slide demo">
    <header class="demo-header">
      <span class="step-pill">Démo {{ $frontmatter.step }}/{{ total }}</span>
      <span class="demo-title">{{ $frontmatter.title }}</span>
      <div class="progress">
        <span
          v-for="n in total"
          :key="n"
          class="seg"
          :class="{ done: n < $frontmatter.step, current: n === $frontmatter.step }"
        />
      </div>
    </header>
    <div class="demo-video">
      <AutoPlayVideo :src="$frontmatter.video" />
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
.demo {
  display: flex;
  flex-direction: column;
  padding: 0.75rem 1rem 2.25rem;
  gap: 0.5rem;
}
.demo-header {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  flex-shrink: 0;
}
.step-pill {
  font-family: monospace;
  font-size: 0.75rem;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: var(--bg);
  background: var(--orange);
  padding: 0.15rem 0.6rem;
  border-radius: 999px;
  white-space: nowrap;
}
.demo-title {
  font-size: 1.125rem;
  font-weight: 700;
  color: var(--text-strong);
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
.progress {
  margin-left: auto;
  display: flex;
  gap: 4px;
}
.seg {
  width: 28px;
  height: 5px;
  border-radius: 3px;
  background: var(--navy-border);
}
.seg.done { background: var(--orange-border); }
.seg.current { background: var(--orange); }
.demo-video {
  flex: 1;
  min-height: 0;
}
</style>
