<script setup>
import { computed } from 'vue'
import { useSlideContext } from '@slidev/client'

const { $clicks } = useSlideContext()

const cx = 420
const cy = 165
const radius = 135
// 5 nodes evenly spaced (72°) on a circle around the core, starting at the top
const at = (i) => {
  const a = (-90 + i * 72) * Math.PI / 180
  return { x: Math.round(cx + radius * Math.cos(a)), y: Math.round(cy + radius * Math.sin(a)) }
}
// Clockwise reveal order, the job node comes last
const nodes = [
  { ...at(0), label: 'Perte de résilience', ref: '(1)' },
  { ...at(1), label: 'Surcharge cognitive' },
  { ...at(2), label: 'Perte de confiance', sub: 'en soi et en l\'autre' },
  { ...at(3), label: 'Perte cognitive', ref: '(2)' },
]
const job = at(4)
const subs = [
  {
    x: job.x - 122, y: job.y + 52,
    title: 'Modèle capitaliste',
    text: 'Sélection naturelle, productivité accrue, pression sur les salaires.',
  },
  {
    x: job.x + 122, y: job.y + 52,
    title: 'Modèle collectiviste',
    text: 'Le travail que la collectivité se choisit est réparti entre tous, donc moins de travail pour tout le monde.',
  },
]

// Zoom on the job node once it appears (click 5)
const scale = 1.6
const zoomed = computed(() => $clicks.value >= 5)
const groupStyle = computed(() => zoomed.value
  ? { transform: `translate(${cx - scale * job.x}px, ${cy - 85 - scale * job.y}px) scale(${scale})` }
  : { transform: 'translate(0px, 0px) scale(1)' })
</script>

<template>
  <svg class="radial" viewBox="0 0 840 330" role="img" aria-label="Les pertes liées à la recherche de performance">
    <g class="world" :style="groupStyle">
      <g :class="['rest', { dim: zoomed }]">
        <circle :cx="cx" :cy="cy" r="85" class="ring" />
        <circle :cx="cx" :cy="cy" :r="radius" class="ring outer" />

        <g v-for="(n, i) in nodes" :key="n.label" v-click="i + 1">
          <path :d="`M${cx},${cy} L${n.x},${n.y}`" class="spoke" />
          <rect :x="n.x - 65" :y="n.y - 21" width="130" height="42" rx="8" class="node" />
          <text :x="n.x" :y="n.y + (n.sub ? -3 : 5)" class="node-title" text-anchor="middle">
            {{ n.label }}<tspan v-if="n.ref" class="ref" dx="4">{{ n.ref }}</tspan>
          </text>
          <text v-if="n.sub" :x="n.x" :y="n.y + 12" class="node-sub" text-anchor="middle">{{ n.sub }}</text>
        </g>

        <circle :cx="cx" :cy="cy" r="46" class="core" />
        <text :x="cx" :y="cy - 2" class="core-title" text-anchor="middle">Toujours</text>
        <text :x="cx" :y="cy + 17" class="core-title" text-anchor="middle">plus de perf.</text>
      </g>

      <g v-click="5">
        <path :d="`M${cx},${cy} L${job.x},${job.y}`" :class="['spoke', 'job-spoke', 'to-core', { gone: zoomed }]" />
        <rect :x="job.x - 65" :y="job.y - 22" width="130" height="44" rx="9" class="node job" />
        <text :x="job.x" :y="job.y + 6" class="node-title" text-anchor="middle">Perte d'emploi ?</text>
      </g>

      <g v-for="s in subs" :key="s.title" v-click="6">
        <path :d="`M${job.x},${job.y + 22} L${s.x},${s.y}`" class="spoke job-spoke" />
        <rect :x="s.x - 117" :y="s.y" width="234" height="78" rx="7" class="node sub-node" />
        <foreignObject :x="s.x - 117" :y="s.y" width="234" height="78">
          <div xmlns="http://www.w3.org/1999/xhtml" class="sub-body">
            <strong>{{ s.title }}</strong>
            <span>{{ s.text }}</span>
          </div>
        </foreignObject>
      </g>
    </g>
  </svg>
</template>

<style scoped>
.radial { width: 100%; height: auto; max-height: 100%; overflow: hidden; }
.world { transition: transform 0.9s cubic-bezier(0.4, 0, 0.2, 1); }
.rest { transition: opacity 0.9s ease; }
.rest.dim { opacity: 0.1; }
.ring { fill: none; stroke: var(--card-border-subtle); stroke-width: 1; stroke-dasharray: 3 5; }
.ring.outer { stroke: var(--navy-border); }
.spoke { stroke: var(--orange-border); stroke-width: 2; }
.job-spoke { stroke: var(--orange); }
.to-core { transition: opacity 0.9s ease; }
.to-core.gone { opacity: 0; }
.core { fill: var(--orange-bg); stroke: var(--orange); stroke-width: 2; }
.core-title { fill: var(--text-strong); font-size: 14px; font-weight: 700; }
.node { fill: var(--bg); stroke: var(--orange-border); stroke-width: 1.5; }
.node.job { stroke: var(--orange); stroke-width: 2; fill: var(--orange-bg); }
.node.sub-node { stroke: var(--navy-border); fill: #1d4a8f; stroke-width: 1; }
.node-title { fill: var(--text-strong); font-size: 13px; font-weight: 700; }
.node-sub { fill: var(--text-muted); font-size: 11px; }
.node-sub.small { font-size: 9.5px; }
.sub-body { display: flex; flex-direction: column; gap: 3px; padding: 8px 12px; font-size: 10px; line-height: 1.3; color: var(--text-muted); }
.sub-body strong { color: var(--text-strong); font-size: 11.5px; }
.ref { fill: var(--orange-light); font-weight: 400; }
</style>
