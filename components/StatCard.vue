<script setup>
defineProps({
  value: { type: String, required: true },
  unit: { type: String, default: '' },
  label: { type: String, default: '' },
})
</script>

<template>
  <div class="card-left-orange stat">
    <div class="figure">
      <span class="value">{{ value }}</span>
      <span v-if="unit" class="unit">{{ unit }}</span>
    </div>
    <div v-if="label" class="label">{{ label }}</div>
    <div v-if="$slots.default" class="card-md body"><slot /></div>
  </div>
</template>

<style scoped>
.stat { display: flex; flex-direction: column; gap: 0.15rem; padding: 0.75rem 1.1rem; }
.figure { display: flex; align-items: baseline; gap: 0.4rem; }
.value {
  font-size: 2.25rem;
  line-height: 1;
  font-weight: 800;
  color: var(--orange);
  white-space: nowrap;
}
.unit { font-size: 1rem; font-weight: 600; color: var(--orange-light); }
.label {
  font-size: 0.7rem;
  font-family: monospace;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  color: var(--text-strong);
}
.body { font-size: 0.8rem; line-height: 1.45; color: var(--text-muted); margin-top: 0.25rem; }
.body :deep(p) { margin: 0 0 0.4rem; font-size: inherit; }
.body :deep(em) { font-size: 0.7rem; color: var(--text-faint); }
</style>
