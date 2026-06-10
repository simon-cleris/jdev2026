---
layout: none
clicks: 10
---

<script setup>
import ApproachRules from '../components/ApproachRules.vue'

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

<div class="flex flex-col px-14 py-4" style="background: #0f172a; color: #e2e8f0; height: 100%; overflow: hidden;">

  <div class="shrink-0 rounded-xl px-8 py-2 mb-3" style="background: rgba(99,102,241,0.1); border: 1px solid rgba(99,102,241,0.4);">
    <div class="text-xs font-mono uppercase tracking-widest mb-1 text-center" style="color: #6366f1;">Mon approche</div>
    <div class="text-sm font-bold leading-snug text-center" style="color: #f1f5f9;">Utilisation comme "capacité de raisonnement" sans aucun savoir</div>
    <div class="text-xs mt-1 text-center" style="color: #94a3b8;">Paradoxe assumé : un "raisonnement" émergent d'un calcul probabiliste ? Ne pas tirer profit de sa base de connaissances ?</div>
  </div>

  <div class="flex gap-6 flex-1 min-h-0 overflow-hidden">
    <ApproachRules :items="techItems" color="#22c55e" title="Approche technique" :click-offset="1" />
    <ApproachRules :items="guardItems" color="#f59e0b" title="Garde-fous" :click-offset="6" />
  </div>

</div>
