<script setup>
import ApproachRules from './ApproachRules.vue'

const techItems = [
  { label: 'Fournir les informations', body: "Ne pas se fonder sur les données d'entraînement -> Assure la maîtrise et améliore grandement la qualité." },
  { label: 'Fournir les outils', body: "Détache des données d'entrainement, apporte du déterminisme, améliore la qualité." },
  { label: 'Restreindre le contexte au minimum', body: "Tout token non pertinent dégrade la qualité." },
  { label: 'Fournir un feedback autonome', body: "Apporte du déterminisme, améliore la qualité, continue jusqu'à la réussite de la tache." },
  { label: 'Automatiser la construction du contexte', body: "Pour implémenter les 4 règles précédentes pour chaque tache." },
]

const guardItems = [
  { label: "Fixer une limite d'utilisation", body: "Analogie data 3G/4G/5G : une limite fixe évite l'effet rebond à chaque nouvelle version." },
  { label: "Utiliser que pour ce qu'on sait faire", body: "Accélère ce qu'on peut faire soi-même mais ne jamais l'utiliser pour une tache que l'on ne maîtrise pas." },
  { label: "Contenir le pouvoir d'action", body: "Supervision de chaque sortie, ou containerisation pour les process autonomes." },
  { label: 'Attention aux données sensibles', body: "Evident." },
]
</script>

<template>
  <div class="slide" style="gap: 0.75rem; padding-top: 1rem;">
    <div class="shrink-0 card-indigo mb-0 text-center">
      <div class="t-label mb-1" style="color: var(--indigo);">Mon approche</div>
      <div class="text-sm font-bold leading-snug" style="color: var(--text-strong);">Utilisation comme "capacité de raisonnement" sans aucun savoir</div>
      <div class="t-body-sm mt-1">Paradoxe assumé : un "raisonnement" émergent d'un calcul probabiliste ? Ne pas tirer profit de sa base de connaissances ?</div>
    </div>
    <div class="flex gap-6 flex-1 min-h-0 overflow-hidden">
      <ApproachRules :items="techItems" color="#22c55e" title="Approche technique" :click-offset="1" />
      <ApproachRules :items="guardItems" color="#f59e0b" title="Garde-fous" :click-offset="6" />
    </div>
  </div>
</template>
