---
layout: none
clicks: 3
---
<div class="h-full max-h-full flex flex-col px-14 py-8 gap-5 overflow-hidden" style="background: #0f172a; color: #e2e8f0;">

  <div class="shrink-0">
    <div class="text-xs font-mono uppercase tracking-widest mb-1" style="color: #22c55e;">Rule 3</div>
    <h1 class="text-3xl font-bold" style="color: #f1f5f9;">Restreindre le contexte au minimum</h1>
    <p class="text-sm mt-1" style="color: #94a3b8;">Tout token non pertinent dégrade la qualité</p>
  </div>

  <div class="flex flex-col gap-4 flex-1 min-h-0 justify-center">

    <div v-click="1" class="rounded-lg px-5 py-4" style="border-left: 3px solid #22c55e; background: rgba(255,255,255,0.04);">
      <div class="font-semibold text-base mb-1" style="color: #f8fafc;">Clear du contexte entre chaque tâche</div>
      <div class="text-sm" style="color: #94a3b8;">
        Le contexte est vidé systématiquement, même entre deux tâches très liées ou similaires.<br>
        On s'en fiche — le contexte sera automatiquement régénéré par la Rule 5.
      </div>
    </div>

    <div v-click="2" class="rounded-lg px-5 py-4" style="border-left: 3px solid #22c55e; background: rgba(255,255,255,0.04);">
      <div class="font-semibold text-base mb-1" style="color: #f8fafc;">Lié au garde-fou : limite d'utilisation</div>
      <div class="text-sm" style="color: #94a3b8;">
        Analogie data 3G/4G/5G — une limite fixe évite l'effet rebond à chaque nouvelle version.<br>
        Le clear du contexte est aussi <span style="color: #f8fafc;">obligatoire</span> par notre règle de limite d'utilisation.
      </div>
    </div>

    <div v-click="3" class="rounded-xl px-5 py-4 text-center" style="background: rgba(99,102,241,0.08); border: 1px solid rgba(99,102,241,0.25);">
      <div class="text-sm font-semibold" style="color: #a5b4fc;">
        Chaque tâche repart de zéro — le contexte minimum est reconstruit automatiquement à chaque fois
      </div>
    </div>

  </div>

</div>
