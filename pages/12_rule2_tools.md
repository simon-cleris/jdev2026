---
layout: none
clicks: 3
---
<div class="h-full max-h-full flex flex-col px-14 py-8 gap-5 overflow-hidden" style="background: #0f172a; color: #e2e8f0;">

  <div class="shrink-0">
    <div class="text-xs font-mono uppercase tracking-widest mb-1" style="color: #22c55e;">Rule 2</div>
    <h1 class="text-3xl font-bold" style="color: #f1f5f9;">Fournir les outils</h1>
    <p class="text-sm mt-1" style="color: #94a3b8;">Détache des données d'entraînement, apporte du déterminisme, améliore la qualité</p>
  </div>

  <div class="flex flex-col gap-3 flex-1 min-h-0 justify-center">

    <div v-click="1" class="rounded-lg px-5 py-4" style="border-left: 3px solid #22c55e; background: rgba(255,255,255,0.04);">
      <div class="flex items-baseline gap-3 mb-1">
        <span class="font-semibold text-base" style="color: #f8fafc;">Accès SSH à l'instrument</span>
        <span class="text-xs font-mono px-2 py-0.5 rounded" style="background: rgba(34,197,94,0.1); color: #86efac;">accès direct au hardware</span>
      </div>
      <div class="text-sm" style="color: #94a3b8;">L'agent peut interagir avec l'instrument réel pour valider le comportement.</div>
    </div>

    <div v-click="2" class="rounded-lg px-5 py-4" style="border-left: 3px solid #22c55e; background: rgba(255,255,255,0.04);">
      <div class="flex items-baseline gap-3 mb-1">
        <span class="font-semibold text-base" style="color: #f8fafc;">Accès Bash au poste de développement</span>
        <span class="text-xs font-mono px-2 py-0.5 rounded" style="background: rgba(34,197,94,0.1); color: #86efac;">garde-fou</span>
      </div>
      <div class="text-sm" style="color: #94a3b8;">
        Toutes les commandes doivent être approuvées —<br>
        sauf <span class="font-mono text-xs px-1.5 py-0.5 rounded" style="background: rgba(255,255,255,0.07); color: #cbd5e1;">find</span> et <span class="font-mono text-xs px-1.5 py-0.5 rounded" style="background: rgba(255,255,255,0.07); color: #cbd5e1;">read</span> à l'intérieur du projet.
      </div>
    </div>

    <div v-click="3" class="rounded-lg px-5 py-4 text-sm" style="background: rgba(245,158,11,0.07); border-left: 3px solid #f59e0b; color: #94a3b8;">
      <span style="color: #fbbf24;">Garde-fou :</span> contenir le pouvoir d'action — supervision de chaque sortie, approbation explicite de toute commande destructive.
    </div>

  </div>

</div>
