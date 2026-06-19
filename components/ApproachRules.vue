<script setup>
defineProps({
  items: { type: Array, required: true },
  title: { type: String, required: true },
  clickOffset: { type: Number, default: 0 },
  variant: { type: String, default: 'orange' },
})
</script>

<template>
  <div class="approach-rules" :class="`approach-rules--${variant}`">
    <div class="approach-rules__header">{{ title }}</div>
    <div class="approach-rules__body">
      <div
        v-for="(item, i) in items"
        :key="i"
        v-click="i + clickOffset"
        class="approach-rules__item"
      >
        <span class="approach-rules__index">{{ i + 1 }}</span>
        <div class="flex-1">
          <span class="font-semibold text-sm" style="color: var(--text-brightest)">{{ item.label }}</span>
          <div class="t-body-sm mt-0.5">
            <span class="approach-rules__arrow">→</span> {{ item.body }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.approach-rules {
  display: flex;
  flex-direction: column;
  flex: 1;
  min-width: 0;
  border-radius: 0.75rem;
  overflow: hidden;
}

.approach-rules--orange {
  border: 1px solid var(--orange-border);
  background: var(--orange-bg);
}

.approach-rules--navy {
  border: 1px solid var(--navy-border);
  background: var(--navy-bg);
}

.approach-rules__header {
  padding: 0.5rem 1rem;
  font-size: 0.75rem;
  font-family: monospace;
  text-transform: uppercase;
  letter-spacing: 0.1em;
}

.approach-rules--orange .approach-rules__header {
  background: var(--orange-bg);
  color: var(--orange);
  border-bottom: 1px solid var(--orange-border);
}

.approach-rules--navy .approach-rules__header {
  background: var(--navy-bg);
  color: var(--navy-light);
  border-bottom: 1px solid var(--navy-border);
}

.approach-rules__body {
  display: flex;
  flex-direction: column;
  gap: 0.25rem;
  padding: 0.75rem;
  flex: 1;
  min-height: 0;
  overflow: hidden;
  justify-content: safe center;
}

.approach-rules__item {
  display: flex;
  align-items: flex-start;
  gap: 0.75rem;
  border-radius: 0.5rem;
  padding: 0.25rem 1rem;
  flex: 1;
  min-height: 0;
  background: var(--card-bg);
}

.approach-rules--orange .approach-rules__item {
  border-left: 3px solid var(--orange);
}

.approach-rules--navy .approach-rules__item {
  border-left: 3px solid var(--navy-light);
}

.approach-rules__index {
  font-family: monospace;
  font-size: 0.875rem;
  font-weight: 700;
  min-width: 1rem;
}

.approach-rules--orange .approach-rules__index {
  color: var(--orange);
}

.approach-rules--navy .approach-rules__index {
  color: var(--navy-light);
}

.approach-rules__arrow {
  margin-right: 0.25rem;
}

.approach-rules--orange .approach-rules__arrow {
  color: var(--orange);
}

.approach-rules--navy .approach-rules__arrow {
  color: var(--navy-light);
}
</style>
