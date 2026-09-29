<script setup>
// Une seule échelle (0–4 %) pour toutes les barres, en % des émissions mondiales de GES.
const MAX = 4

const rows = [
  { label: 'Numérique total', note: 'base 4 % (2020), supposée stable', a: [4, 4], b: [4, 4], ta: '4 %', tb: '4 %' },
  { label: 'Data centers', note: '2024 : 16 % du numérique · 2030 : ×2,3 (conso IEA 415 → 945 TWh)', a: [0.64, 0.64], b: [1.46, 1.46], ta: '~0,6 %', tb: '~1,5 %' },
  { label: 'IA', note: '5–15 % puis 35–50 % des data centers (IEA)', a: [0.03, 0.1], b: [0.5, 0.7], ta: '0,03–0,1 %', tb: '0,5–0,7 %' },
]

const pct = (v) => `${(v / MAX) * 100}%`
const span = ([lo, hi]) => `${((hi - lo) / MAX) * 100}%`
</script>

<template>
  <div class="chart card-navy">
    <div class="chart-label">Part des émissions mondiales de GES — 2024 → 2030</div>
    <div class="legend">
      <span><i class="dot y2024" />2024</span>
      <span><i class="dot y2030" />2030</span>
    </div>

    <div v-for="r in rows" :key="r.label" class="row">
      <div class="row-label">
        <div class="name">{{ r.label }}</div>
        <div class="of">{{ r.note }}</div>
      </div>
      <div class="bars">
        <div v-if="r.single" class="bar-line">
          <div class="track">
            <div class="fill ysingle" :style="{ width: pct(r.single[0]) }" />
          </div>
          <span class="val strong">{{ r.ts }}</span>
        </div>
        <template v-else>
        <div class="bar-line">
          <div class="track">
            <div class="fill y2024" :style="{ width: pct(r.a[0]) }" />
            <div class="fill y2024 range" :style="{ width: span(r.a) }" />
          </div>
          <span class="val">{{ r.ta }}</span>
        </div>
        <div class="bar-line">
          <div class="track">
            <div class="fill y2030" :style="{ width: pct(r.b[0]) }" />
            <div class="fill y2030 range" :style="{ width: span(r.b) }" />
          </div>
          <span class="val strong">{{ r.tb }}</span>
        </div>
        </template>
      </div>
    </div>
  </div>
</template>

<style scoped>
.chart {
  padding: 0.6rem 1.25rem;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}
.chart-label {
  font-size: 0.65rem;
  font-family: monospace;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: var(--orange-light);
}
.grid-total {
  display: block;
  margin-top: 0.15rem;
  color: var(--text-muted);
  text-transform: none;
  letter-spacing: 0;
}
.legend {
  display: flex;
  gap: 1rem;
  align-items: center;
  font-size: 0.65rem;
  color: var(--text-muted);
}
.dot {
  display: inline-block;
  width: 0.6rem;
  height: 0.6rem;
  border-radius: 2px;
  margin-right: 0.3rem;
}
.y2024 { background: var(--text-faint); }
.y2030 { background: var(--orange); }
.ysingle { background: var(--text-strong); }
.row {
  display: grid;
  grid-template-columns: 11rem 1fr;
  align-items: center;
  gap: 0.75rem;
  padding-top: 0.4rem;
  border-top: 1px solid var(--navy-border);
}
.name { font-size: 0.85rem; font-weight: 600; color: var(--text-strong); }
.of { font-size: 0.65rem; color: var(--text-muted); line-height: 1.25; }
.bars { display: flex; flex-direction: column; gap: 0.25rem; }
.bar-line { display: flex; align-items: center; gap: 0.5rem; }
.track {
  flex: 1;
  height: 0.6rem;
  display: flex;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 3px;
  overflow: hidden;
}
.fill { height: 100%; }
.range { opacity: 0.45; }
.val {
  width: 4.6rem;
  font-size: 0.7rem;
  font-family: monospace;
  color: var(--text-muted);
}
.val.strong { color: var(--text-strong); font-weight: 700; }
</style>
