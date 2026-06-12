---
layout: none
clicks: 4
---
<div class="h-full max-h-full flex flex-col px-14 py-8 gap-5 overflow-hidden" style="background: #0f172a; color: #e2e8f0;">

  <div class="shrink-0">
    <div class="text-xs font-mono uppercase tracking-widest mb-1" style="color: #22c55e;">Rule 5</div>
    <h1 class="text-3xl font-bold" style="color: #f1f5f9;">Automatiser la construction du contexte</h1>
    <p class="text-sm mt-1" style="color: #94a3b8;">Chargement incrémental et récupération autonome — reconstruit à chaque tâche</p>
  </div>

  <div class="flex gap-5 flex-1 min-h-0 overflow-hidden">

    <div class="flex flex-col gap-3 flex-1">

      <div v-click="1" class="rounded-lg px-4 py-3" style="border-left: 3px solid #22c55e; background: rgba(255,255,255,0.04);">
        <div class="font-semibold text-sm mb-1" style="color: #f8fafc;">Fichier racine minimal</div>
        <ul class="text-xs space-y-1" style="color: #94a3b8;">
          <li><span style="color: #22c55e;">→</span> Lien vers l'index de la documentation</li>
          <li><span style="color: #22c55e;">→</span> Lien vers l'index de la spec technique</li>
          <li><span style="color: #22c55e;">→</span> Master rules du projet</li>
          <li><span style="color: #22c55e;">→</span> Description en une ligne de chaque sous-dossier</li>
        </ul>
      </div>

      <div v-click="2" class="rounded-lg px-4 py-3" style="border-left: 3px solid #22c55e; background: rgba(255,255,255,0.04);">
        <div class="font-semibold text-sm mb-1" style="color: #f8fafc;">CLAUDE.md par sous-dossier</div>
        <div class="text-xs" style="color: #94a3b8;">
          Chargé automatiquement dès qu'un fichier du dossier est lu ou qu'une commande bash y est exécutée.<br>
          Contient la spec fonctionnelle et les choix techniques des scripts — jamais de code, jamais de référence de ligne.
        </div>
      </div>

      <div v-click="3" class="rounded-lg px-4 py-3" style="border-left: 3px solid #6366f1; background: rgba(99,102,241,0.06);">
        <div class="font-semibold text-sm mb-1" style="color: #a5b4fc;">Ces fichiers sont générés par l'agent lui-même</div>
        <div class="text-xs" style="color: #94a3b8;">À partir de la documentation et de la spec, avant toute implémentation.</div>
      </div>

    </div>

    <div v-click="4" class="flex-1 rounded-lg overflow-auto px-4 py-3" style="background: rgba(255,255,255,0.03); border: 1px solid rgba(255,255,255,0.07); font-family: monospace;">
      <div class="text-xs mb-2" style="color: #64748b;">common/CLAUDE.md — exemple</div>
      <div class="text-xs leading-relaxed" style="color: #cbd5e1;">
        <span style="color: #6366f1;">##</span> common/state_machine.py<br><br>
        <span style="color: #94a3b8;">Service — computes flight phase from aircraft speed,<br>publishes state transitions and flight events.</span><br><br>
        <span style="color: #6366f1;">###</span> State machine Behaviour<br><br>
        <span style="color: #94a3b8;">- Subscribes to: </span><span style="color: #86efac;">AircraftData</span><span style="color: #94a3b8;">, </span><span style="color: #86efac;">ModuleDisconnected</span><br>
        <span style="color: #94a3b8;">- STOPPED: speed &lt; 3 kn</span><br>
        <span style="color: #94a3b8;">- MOVING: 3 ≤ speed &lt; 50 kn</span><br>
        <span style="color: #94a3b8;">- CRUISE: speed ≥ 250 kn</span><br>
        <span style="color: #94a3b8;">- Publishes: </span><span style="color: #86efac;">StateTransition</span><span style="color: #94a3b8;">, </span><span style="color: #86efac;">LANDING</span><br>
      </div>
    </div>

  </div>

</div>
