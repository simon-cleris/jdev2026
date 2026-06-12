---
layout: none
clicks: 3
---
<div class="h-full max-h-full flex flex-col px-14 py-8 gap-5 overflow-hidden" style="background: #0f172a; color: #e2e8f0;">

  <div class="shrink-0">
    <div class="text-xs font-mono uppercase tracking-widest mb-1" style="color: #22c55e;">Rule 1</div>
    <h1 class="text-3xl font-bold" style="color: #f1f5f9;">Fournir les informations</h1>
    <p class="text-sm mt-1" style="color: #94a3b8;">Ne pas se fonder sur les données d'entraînement — assure la maîtrise et améliore grandement la qualité</p>
  </div>

  <div class="flex flex-col gap-3 flex-1 min-h-0 justify-center">

    <div v-click="1" class="rounded-lg px-5 py-4" style="border-left: 3px solid #22c55e; background: rgba(255,255,255,0.04);">
      <div class="font-semibold text-base mb-1" style="color: #f8fafc;">Spec fonctionnelle = la documentation</div>
      <div class="text-sm" style="color: #94a3b8;">
        Rédaction de la spécification fonctionnelle qui sert également de documentation pour le logiciel embarqué.<br>
        Manuels techniques de tous les composants hardware en annexe.
      </div>
    </div>

    <div v-click="2" class="rounded-lg px-5 py-4" style="border-left: 3px solid #22c55e; background: rgba(255,255,255,0.04);">
      <div class="font-semibold text-base mb-1" style="color: #f8fafc;">Publiée comme site web</div>
      <div class="text-sm" style="color: #94a3b8;">
        Format <span class="font-mono text-xs px-1.5 py-0.5 rounded" style="background: rgba(34,197,94,0.1); color: #86efac;">.md</span> fourni aux commanditaires sous forme de site — boucle de conformité en phase avec l'approche DevOps.
      </div>
    </div>

    <div v-click="3" class="rounded-lg px-5 py-4" style="border-left: 3px solid #22c55e; background: rgba(255,255,255,0.04);">
      <div class="font-semibold text-base mb-1" style="color: #f8fafc;">Spec technique</div>
      <div class="text-sm" style="color: #94a3b8;">
        Choix technologiques et architecturaux pour répondre aux cahiers des charges — rédigée avant toute ligne de code.
      </div>
    </div>

  </div>

</div>
