<script setup>
defineProps({
  items: { type: Array, required: true },
})
</script>

<template>
  <div class="h-full flex flex-col justify-center px-16 gap-2">
    <div class="font-mono text-xs uppercase tracking-widest mb-4" style="color: var(--orange)">Sommaire</div>
    <div
      v-for="(item, i) in items"
      :key="i"
      v-click="i + 1"
      class="flex items-baseline gap-6 py-2 border-b"
      style="border-color: var(--card-border-subtle)"
    >
      <span class="font-mono font-bold text-lg w-8 shrink-0" style="color: var(--navy-light)">{{ String(i + 1).padStart(2, '0') }}</span>
      <span class="text-lg" style="color: var(--text-strong)">{{ item }}</span>
    </div>
  </div>
</template>
