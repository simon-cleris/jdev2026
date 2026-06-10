---
layout: none
clicks: 6
---

<script setup>
const errors = [
  {
    label: 'Librairie non maîtrisée',
    detail: 'pydantic-ai',
    consequence: 'Bad patterns non détectés, propagés silencieusement dans tout le code',
  },
  {
    label: 'Contexte non structuré',
    detail: 'codebase entière dans le prompt',
    consequence: 'Coût élevé, duplication de code, mauvaise qualité',
  },
  {
    label: 'Pas de spec fonctionnelle',
    detail: 'démarrage sans définition complète',
    consequence: 'Duplication de code, périmètre instable',
  },
  {
    label: 'Spec technique insuffisante',
    detail: 'choix architecturaux laissés à l\'IA',
    consequence: 'Overengineering incontrôlé',
  },
  {
    label: 'Feedback manuel',
    detail: 'validation par test humain uniquement',
    consequence: 'Mauvaise qualité et temps perdu en boucles de correction',
  },
]
</script>

<div class="h-full max-h-full flex flex-col px-14 py-6 overflow-hidden" style="background: #0f172a; color: #e2e8f0;">
  <div class="mb-4">
    <p class="text-sm font-mono" style="color: #64748b;">Juin 2025 — Génération de rapports LaTeX à partir de données actualisées</p>
    <h1 class="text-3xl font-bold mt-1" style="color: #f1f5f9;">Premier projet : les erreurs</h1>
  </div>

  <div class="flex flex-col gap-2 flex-1 min-h-0 justify-center overflow-hidden">
    <div
      v-for="(error, i) in errors"
      :key="i"
      v-click="i + 1"
      class="flex items-start gap-4 rounded-lg px-5 py-2"
      style="border-left: 3px solid #ef4444; background: rgba(255,255,255,0.04);"
    >
      <div class="flex-1">
        <div class="flex items-baseline gap-3">
          <span class="font-semibold text-base" style="color: #f8fafc;">{{ error.label }}</span>
          <span class="text-xs font-mono px-2 py-0.5 rounded" style="background: rgba(239,68,68,0.15); color: #fca5a5;">{{ error.detail }}</span>
        </div>
        <div class="text-sm mt-1" style="color: #94a3b8;">
          <span style="color: #f97316;">→</span> {{ error.consequence }}
        </div>
      </div>
    </div>
  </div>

  <div
    v-click="6"
    class="mt-4 rounded-lg px-5 py-3 text-sm"
    style="background: rgba(34,197,94,0.08); border: 1px solid rgba(34,197,94,0.2); color: #86efac;"
  >
    Malgré tout : projet simple, objectif atteint, délai négligeable. Sur un projet plus grand...
  </div>
</div>
