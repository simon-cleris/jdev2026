<script setup>
const inputs = [
  { y: 28, ty: 120, lines: ['Contexte minimal', 'CLAUDE.md global + par dossier'] },
  { y: 110, ty: 146, lines: ['Outils', 'bash · SSH vers l\'instrument'] },
  { y: 192, ty: 172, pull: true, lines: ['Specs détaillées (markdown)', 'consultées à la demande'] },
]
const outputs = [
  { y: 28, sy: 120, lines: ['Driver + mock', 'du hardware'] },
  { y: 110, sy: 146, lines: ['Module + tests', 'intégration et end-to-end'] },
  { y: 192, sy: 172, lines: ['CLAUDE.md mis à jour', 'avant toute implémentation'] },
]
</script>

<template>
  <svg class="loop" viewBox="0 0 840 390" role="img" aria-label="Boucle de feedback de l'agent">
    <defs>
      <marker id="arrow" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto-start-reverse">
        <path d="M0,0 L10,5 L0,10 z" class="arrow-head" />
      </marker>
    </defs>

    <g v-click="1">
      <text x="115" y="14" class="col-label" text-anchor="middle">DONNÉ À L'AGENT</text>
      <g v-for="b in inputs" :key="b.y">
        <rect x="0" :y="b.y" width="230" height="70" rx="8" :class="['box', { pull: b.pull }]" />
        <text x="115" :y="b.y + 30" class="title" text-anchor="middle">{{ b.lines[0] }}</text>
        <text x="115" :y="b.y + 50" class="sub" text-anchor="middle">{{ b.lines[1] }}</text>
        <path v-if="!b.pull" :d="`M230,${b.y + 35} L323,${b.ty}`" class="link" marker-end="url(#arrow)" />
        <path v-else :d="`M323,${b.ty} L232,${b.y + 35}`" class="link pull-link" marker-end="url(#arrow)" />
      </g>
    </g>

    <g v-click="2">
      <rect x="325" y="96" width="190" height="100" rx="12" class="box agent" />
      <text x="420" y="140" class="agent-title" text-anchor="middle">Agent</text>
      <text x="420" y="162" class="sub" text-anchor="middle">contexte vidé entre tâches</text>
      <rect x="325" y="28" width="190" height="44" rx="8" class="box human" />
      <text x="420" y="47" class="title" text-anchor="middle">Humain</text>
      <text x="420" y="63" class="sub" text-anchor="middle">approuve chaque commande</text>
      <path d="M420,72 L420,94" class="link" marker-end="url(#arrow)" />
    </g>

    <g v-click="3">
      <text x="725" y="14" class="col-label" text-anchor="middle">GÉNÉRÉ</text>
      <g v-for="b in outputs" :key="b.y">
        <rect x="610" :y="b.y" width="230" height="70" rx="8" class="box out" />
        <text x="725" :y="b.y + 30" class="title" text-anchor="middle">{{ b.lines[0] }}</text>
        <text x="725" :y="b.y + 50" class="sub" text-anchor="middle">{{ b.lines[1] }}</text>
        <path :d="`M517,${b.sy} L608,${b.y + 35}`" class="link" marker-end="url(#arrow)" />
      </g>
    </g>

    <g v-click="4">
      <path d="M725,262 L725,338 L542,338" class="link loop-link" marker-end="url(#arrow)" />
      <rect x="300" y="310" width="240" height="56" rx="8" class="box feedback" />
      <text x="420" y="334" class="title" text-anchor="middle">Feedback autonome</text>
      <text x="420" y="353" class="sub" text-anchor="middle">instrument réel · mock · tests</text>
      <path d="M420,310 L420,198" class="link loop-link" marker-end="url(#arrow)" />
      <text x="432" y="262" class="loop-label">boucle jusqu'à la réussite</text>
    </g>
  </svg>
</template>

<style scoped>
.loop { width: 100%; height: auto; max-height: 100%; }
.box { fill: var(--card-bg); stroke: var(--card-border-subtle); stroke-width: 1.5; }
.agent { fill: var(--orange-bg); stroke: var(--orange); stroke-width: 2; }
.out { stroke: var(--orange-border); }
.feedback { stroke: var(--orange); stroke-dasharray: 5 4; }
.pull { stroke: var(--orange-border); stroke-dasharray: 5 4; }
.pull-link { stroke: var(--orange-light); stroke-dasharray: 5 4; }
.human { stroke: var(--navy-border); }
.title { fill: var(--text-strong); font-size: 14px; font-weight: 700; }
.agent-title { fill: var(--text-strong); font-size: 22px; font-weight: 700; }
.sub { fill: var(--text-muted); font-size: 12.5px; }
.col-label { fill: var(--orange); font-family: monospace; font-size: 12px; letter-spacing: 0.08em; }
.link { fill: none; stroke: var(--text-faint); stroke-width: 1.8; }
.loop-link { stroke: var(--orange); stroke-width: 2.2; }
.arrow-head { fill: var(--text-faint); }
.loop-label { fill: var(--orange-light); font-size: 12.5px; font-style: italic; }
</style>
