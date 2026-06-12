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
    detail: "choix architecturaux laissés à l'IA",
    consequence: 'Overengineering incontrôlé',
  },
  {
    label: 'Feedback manuel',
    detail: 'validation par test humain uniquement',
    consequence: 'Mauvaise qualité et temps perdu en boucles de correction',
  },
]
</script>

<template>
  <div class="slide" style="gap: 1rem;">
    <div class="shrink-0">
      <p class="t-label" style="color: var(--text-faint);">Juin 2025 — Génération de rapports LaTeX à partir de données actualisées</p>
      <h1 class="t-h1" style="margin-top: 0.25rem;">Premier projet : les erreurs</h1>
    </div>

    <div class="flex flex-col gap-2 flex-1 min-h-0 justify-center overflow-hidden">
      <div
        v-for="(error, i) in errors"
        :key="i"
        v-click="i + 1"
        class="card-left-red flex items-start gap-4"
        style="padding-top: 0.5rem; padding-bottom: 0.5rem;"
      >
        <div class="flex-1">
          <div class="flex items-baseline gap-3">
            <span class="font-semibold text-base" style="color: var(--text-brightest);">{{ error.label }}</span>
            <span class="text-xs font-mono px-2 py-0.5 rounded" style="background: rgba(239,68,68,0.15); color: var(--red-light);">{{ error.detail }}</span>
          </div>
          <div class="t-body mt-1">
            <span class="arrow-orange">→</span> {{ error.consequence }}
          </div>
        </div>
      </div>
    </div>

    <div v-click="6" class="card-green-outline t-body shrink-0" style="color: var(--green-light);">
      Malgré tout : projet simple, objectif atteint, délai négligeable. Sur un projet plus grand...
    </div>
  </div>
</template>
