---
layout: none
clicks: 6
---

<script setup>
const steps = [
  {
    label: 'Plan d\'implémentation',
    detail: 'Rédaction en phase indépendante',
    human: true,
  },
  {
    label: 'Driver + Mock',
    detail: 'Template, driver réel, driver mock',
    human: false,
  },
  {
    label: 'Tests d\'intégration',
    detail: 'Validation sur hardware réel ou mock',
    human: true,
  },
  {
    label: 'Module',
    detail: 'Non rattaché au hardware, répond à la spec',
    human: false,
  },
  {
    label: 'Tests de validation spec',
    detail: 'CFR / SFR depuis mock ou réel',
    human: true,
  },
  {
    label: 'Tests end-to-end',
    detail: 'Simulations de vol, configurations variées',
    human: false,
  },
]
</script>

<div class="h-full max-h-full flex flex-col px-14 py-8 gap-5 overflow-hidden" style="background: #0f172a; color: #e2e8f0;">

  <div class="shrink-0">
    <div class="text-xs font-mono uppercase tracking-widest mb-1" style="color: #22c55e;">Rule 4</div>
    <h1 class="text-3xl font-bold" style="color: #f1f5f9;">Fournir un feedback autonome</h1>
    <p class="text-sm mt-1" style="color: #94a3b8;">Apporte du déterminisme, améliore la qualité, continue jusqu'à la réussite de la tâche</p>
  </div>

  <div class="flex flex-col gap-2 flex-1 min-h-0 justify-center">
    <div
      v-for="(step, i) in steps"
      :key="i"
      v-click="i + 1"
      class="flex items-center gap-4 rounded-lg px-5 py-2"
      style="background: rgba(255,255,255,0.04);"
    >
      <div class="text-xs font-mono w-4 text-right shrink-0" style="color: #475569;">{{ i + 1 }}</div>
      <div class="flex-1">
        <div class="flex items-baseline gap-3">
          <span class="font-semibold text-sm" style="color: #f8fafc;">{{ step.label }}</span>
          <span class="text-xs" style="color: #64748b;">{{ step.detail }}</span>
        </div>
      </div>
      <div
        class="text-xs px-2 py-0.5 rounded font-mono shrink-0"
        :style="step.human
          ? 'background: rgba(245,158,11,0.12); color: #fbbf24;'
          : 'background: rgba(34,197,94,0.1); color: #86efac;'"
      >
        {{ step.human ? 'feedback humain' : 'autonome' }}
      </div>
    </div>
  </div>

</div>
