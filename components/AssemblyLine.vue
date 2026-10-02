<script setup>
// Irregular raw parts go in, identical standardized parts come out.
const raw = [
  { d: 'M0,-14 L13,10 L-13,10 Z' },
  { d: 'M0,-13 A13,13 0 1 1 -0.1,-13 Z' },
  { d: 'M0,-15 L14,-4 L9,12 L-9,12 L-14,-4 Z' },
  { d: 'M-12,-8 Q0,-18 12,-8 Q16,6 4,12 Q-10,14 -12,-8 Z' },
]
const duration = 8
const spacing = duration / raw.length
</script>

<template>
  <svg class="line" viewBox="0 0 600 120" role="img" aria-label="Chaîne de production automatisée">
    <!-- belt -->
    <rect x="0" y="86" width="600" height="8" rx="4" class="belt" />
    <line x1="0" y1="90" x2="600" y2="90" class="belt-dash" />
    <g v-for="x in [20, 120, 220, 320, 420, 520]" :key="x" :transform="`translate(${x} 104)`">
      <g class="roller">
        <circle r="9" class="roller-ring" />
        <path d="M-9,0 H9 M0,-9 V9" class="roller-spoke" />
      </g>
    </g>

    <!-- parts -->
    <g class="parts">
      <g v-for="(r, i) in raw" :key="i" class="part" :style="{ animationDelay: `${-(i * spacing) - 1}s` }">
        <g transform="translate(0 66)">
          <path :d="r.d" class="rough" :style="{ animationDelay: `${-(i * spacing) - 1}s` }" />
          <rect x="-13" y="-13" width="26" height="26" rx="3" class="std" :style="{ animationDelay: `${-(i * spacing) - 1}s` }" />
        </g>
      </g>
    </g>

    <!-- press -->
    <g transform="translate(300 0)">
      <rect x="-30" y="0" width="60" height="10" rx="3" class="frame" />
      <g class="press">
        <rect x="-4" y="10" width="8" height="26" class="arm" />
        <rect x="-20" y="36" width="40" height="12" rx="3" class="head" />
      </g>
    </g>
  </svg>
</template>

<style scoped>
.line { width: 100%; height: auto; overflow: hidden; }
.belt { fill: var(--card-bg); stroke: var(--navy-border); stroke-width: 1.5; }
.belt-dash { stroke: var(--text-faint); stroke-width: 1.5; stroke-dasharray: 8 10; animation: belt 0.8s linear infinite; }
.roller-ring { fill: var(--bg); stroke: var(--navy-border); stroke-width: 1.5; }
.roller-spoke { stroke: var(--text-faint); stroke-width: 1.5; }
.roller { animation: spin 2s linear infinite; }

.part { animation: travel 8s linear infinite; }
.rough { fill: none; stroke: var(--orange-light); stroke-width: 2; stroke-linejoin: round; animation: rough-vis 8s linear infinite; }
.std { fill: var(--orange-bg); stroke: var(--orange); stroke-width: 2; animation: std-vis 8s linear infinite; }

.frame { fill: var(--navy-border); }
.arm { fill: var(--text-faint); }
.head { fill: var(--orange); }
.press { animation: stamp 2s ease-in-out infinite; }

.roller { transform-box: fill-box; transform-origin: center; }

@keyframes travel { from { transform: translateX(-30px); } to { transform: translateX(630px); } }
@keyframes rough-vis { 0%, 47% { opacity: 1; } 49%, 100% { opacity: 0; } }
@keyframes std-vis { 0%, 47% { opacity: 0; } 49%, 100% { opacity: 1; } }
@keyframes stamp { 0%, 35%, 100% { transform: translateY(0); } 50% { transform: translateY(24px); } 65% { transform: translateY(0); } }
@keyframes belt { to { stroke-dashoffset: -18; } }
@keyframes spin { to { transform: rotate(360deg); } }

@media (prefers-reduced-motion: reduce) {
  .part, .rough, .std, .press, .roller, .belt-dash { animation: none; }
}
</style>
