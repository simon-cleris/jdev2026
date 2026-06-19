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
    <div class="flex flex-col gap-2 flex-1 min-h-0 justify-center">
      <div
        v-for="(step, i) in $frontmatter.steps"
        :key="i"
        v-click="i + 1"
        class="card flex items-center gap-4"
      >
        <div class="text-xs font-mono w-4 text-right shrink-0" style="color: #475569;">{{ i + 1 }}</div>
        <div class="flex-1">
          <div class="flex items-baseline gap-3">
            <span class="font-semibold text-sm" style="color: var(--text-brightest);">{{ step.label }}</span>
            <span class="t-body-sm" style="color: var(--text-faint);">{{ step.detail }}</span>
          </div>
        </div>
        <div
          class="text-xs px-2 py-0.5 rounded font-mono shrink-0"
          :style="step.human
            ? 'background: var(--navy-bg); color: var(--navy-light);'
            : 'background: var(--orange-bg); color: var(--orange-light);'"
        >
          {{ step.human ? 'feedback humain' : 'autonome' }}
        </div>
      </div>
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
