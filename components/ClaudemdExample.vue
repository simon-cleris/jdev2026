<template>
  <div class="flex-1 rounded-lg overflow-auto px-4 py-3" style="background: var(--card-bg-code); border: 1px solid var(--card-border-subtle); font-family: monospace;">
    <div class="t-body-sm mb-2" style="color: var(--text-faint);">common/CLAUDE.md — exemple</div>
    <div class="text-xs leading-relaxed" style="color: #cbd5e1;">
      <span style="color: var(--indigo);">##</span> common/state_machine.py<br><br>
      <span style="color: var(--text-muted);">Service — computes flight phase from aircraft speed,<br>publishes state transitions and flight events.</span><br><br>
      <span style="color: var(--indigo);">###</span> State machine Behaviour<br><br>
      <span style="color: var(--text-muted);">- Subscribes to: </span><span style="color: var(--green-light);">AircraftData</span><span style="color: var(--text-muted);">, </span><span style="color: var(--green-light);">ModuleDisconnected</span><br>
      <span style="color: var(--text-muted);">- STOPPED: speed &lt; 3 kn</span><br>
      <span style="color: var(--text-muted);">- MOVING: 3 ≤ speed &lt; 50 kn</span><br>
      <span style="color: var(--text-muted);">- CRUISE: speed ≥ 250 kn</span><br>
      <span style="color: var(--text-muted);">- Publishes: </span><span style="color: var(--green-light);">StateTransition</span><span style="color: var(--text-muted);">, </span><span style="color: var(--green-light);">LANDING</span><br>
    </div>
  </div>
</template>
