<template>
  <div class="slidev-layout dark-slide slide" style="gap: 1.5rem;">
    <slot name="intro" />
    <slot name="transition" />
    <div class="grid gap-2 flex-1 min-h-0" style="grid-template-columns: repeat(3, 1fr); align-content: start;">
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
