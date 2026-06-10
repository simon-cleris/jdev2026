---
layout: none
clicks: 11
---

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

<div class="h-full max-h-full flex flex-col px-14 py-8 gap-6 overflow-hidden" style="background: #0f172a; color: #e2e8f0;">

  <div v-click="0" class="rounded-xl px-8 py-5 text-center" style="background: rgba(99,102,241,0.1); border: 1px solid rgba(99,102,241,0.4);">
    <div class="text-xs font-mono uppercase tracking-widest mb-2" style="color: #6366f1;">Mécanique</div>
    <div class="text-2xl font-bold" style="color: #f1f5f9;">Prédit le token suivant le plus probable compte tenu des tokens précédents et de ses données d'entraînement</div>
    <div class="text-base mt-2" style="color: #94a3b8;">Pas de raisonnement, pas de compréhension : de la statistique à partir d'une immense base de données</div>
  </div>

  <div v-click="1" class="text-center text-base font-semibold" style="color: #cbd5e1;">
    Ce qui nous fait naturellement penser qu'on peut l'utiliser comme <span style="color: #f1f5f9;">base de connaissance</span>
  </div>

  <div class="grid gap-2 flex-1 min-h-0" style="grid-template-columns: repeat(3, 1fr); align-content: start;">
    <div
      v-for="(p, i) in problems"
      :key="i"
      v-click="i + 2"
      class="rounded-lg px-4 py-2"
      style="background: rgba(239,68,68,0.07); border-left: 3px solid #ef4444;"
    >
      <div class="font-semibold text-sm" style="color: #fca5a5;">{{ p.label }}</div>
      <div class="text-xs mt-0.5" style="color: #94a3b8;">{{ p.body }}</div>
    </div>
  </div>

</div>
