<script setup>
defineProps({
  items: { type: Array, required: true },
  color: { type: String, required: true },
  title: { type: String, required: true },
  clickOffset: { type: Number, default: 0 },
})
</script>

<template>
  <div class="flex flex-col flex-1 min-w-0 rounded-xl overflow-hidden" :style="`border: 1px solid ${color}4d; background: ${color}08`">
    <div class="px-4 py-2 text-xs font-mono uppercase tracking-widest" :style="`background: ${color}1a; color: ${color}; border-bottom: 1px solid ${color}33`">
      {{ title }}
    </div>
    <div class="flex flex-col gap-1 p-3 flex-1 min-h-0 overflow-hidden" style="justify-content: safe center;">
      <div
        v-for="(item, i) in items"
        :key="i"
        v-click="i + clickOffset"
        class="flex items-start gap-3 rounded-lg px-4 py-1 flex-1 min-h-0"
        :style="`border-left: 3px solid ${color}; background: var(--card-bg)`"
      >
        <span class="font-mono text-sm font-bold" :style="`color: ${color}; min-width: 1rem`">{{ i + 1 }}</span>
        <div class="flex-1">
          <span class="font-semibold text-sm" style="color: var(--text-brightest)">{{ item.label }}</span>
          <div class="t-body-sm mt-0.5">
            <span :style="`color: ${color}`">→</span> {{ item.body }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
