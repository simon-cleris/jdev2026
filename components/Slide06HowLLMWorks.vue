<script setup>
const problems = [
  { label: 'Dépendance / Dette technique', body: "Analogie Google effect : déléguer atrophie la mémoire et les réflexes." },
  { label: 'Hallucination / Qualité imprévisible', body: "Le modèle invente avec confiance et ne signale pas ses erreurs." },
  { label: 'Dette technique', body: "Du code non maîtrisé s'accumule, les bad patterns se propagent." },
  { label: 'Perte de compétences', body: "On ne sait plus faire ce qu'on délègue." },
  { label: 'Qualité imprévisible', body: "Sans expertise pour juger la sortie, impossible de détecter les erreurs." },
  { label: 'Risque juridique', body: "Droits sur les sorties incertains, données envoyées à des tiers." },
  { label: 'Données exposées', body: "Données personnelles et stratégiques chez un fournisseur privé." },
  { label: 'Impact environnemental', body: "Coût énergétique massif à l'entraînement et à l'inférence." },
  { label: 'Dépendance fournisseur', body: "Couplage fort à un acteur privé hors de tout contrôle." },
]
</script>

<template>
  <div class="slide" style="gap: 1.5rem;">
    <div v-click="0" class="card-indigo shrink-0 text-center">
      <div class="t-label mb-2" style="color: var(--indigo);">Mécanique</div>
      <div class="text-2xl font-bold" style="color: var(--text-strong);">Prédit le token suivant le plus probable compte tenu des tokens précédents et de ses données d'entraînement</div>
      <div class="text-base mt-2" style="color: var(--text-muted);">Pas de raisonnement, pas de compréhension : de la statistique à partir d'une immense base de données</div>
    </div>

    <div v-click="1" class="text-center text-base font-semibold shrink-0" style="color: #cbd5e1;">
      Ce qui nous fait naturellement penser qu'on peut l'utiliser comme <span style="color: var(--text-strong);">base de connaissance</span>
    </div>

    <div class="grid gap-2 flex-1 min-h-0" style="grid-template-columns: repeat(3, 1fr); align-content: start;">
      <div
        v-for="(p, i) in problems"
        :key="i"
        v-click="i + 2"
        class="card-left-red"
        style="padding-top: 0.5rem; padding-bottom: 0.5rem;"
      >
        <div class="font-semibold text-sm" style="color: var(--red-light);">{{ p.label }}</div>
        <div class="t-body-sm mt-0.5">{{ p.body }}</div>
      </div>
    </div>
  </div>
</template>
