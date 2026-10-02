<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'

const prompt = ['Le', 'ciel', 'est']
const steps = [
  { cands: [['bleu', 62], ['gris', 21], ['clair', 11]], pick: 0 },
  { cands: [[',', 41], ['et', 33], ['aujourd\'hui', 14]], pick: 0 },
  { cands: [['sans', 38], ['parsemé', 24], ['dégagé', 19]], pick: 0 },
  { cands: [['nuages', 71], ['nuage', 15], ['limite', 6]], pick: 0 },
]

const written = ref([])
const step = ref(-1)
const picked = ref(false)

let stopped = false
const wait = (ms) => new Promise((r) => setTimeout(r, ms))

async function run() {
  while (!stopped) {
    written.value = []
    step.value = -1
    picked.value = false
    await wait(900)
    for (let i = 0; i < steps.length && !stopped; i++) {
      step.value = i
      picked.value = false
      await wait(1100)
      picked.value = true
      await wait(700)
      written.value.push(steps[i].cands[steps[i].pick][0])
      await wait(250)
    }
    step.value = -1
    await wait(2200)
  }
}

onMounted(run)
onBeforeUnmount(() => { stopped = true })
</script>

<template>
  <div class="tokens">
    <div class="line">
      <span v-for="t in prompt" :key="t" class="tok">{{ t }}</span>
      <span v-for="(t, i) in written" :key="`w${i}`" class="tok new">{{ t }}</span>
      <span class="cursor" />
    </div>
    <div class="cands">
      <template v-if="step >= 0">
        <div
          v-for="(c, i) in steps[step].cands"
          :key="`${step}-${i}`"
          :class="['cand', { chosen: picked && i === steps[step].pick, faded: picked && i !== steps[step].pick }]"
          :style="{ '--p': c[1] + '%' }"
        >
          <span class="word">{{ c[0] }}</span>
          <span class="pct">{{ c[1] }} %</span>
        </div>
      </template>
    </div>
  </div>
</template>

<style scoped>
.tokens { display: flex; flex-direction: column; align-items: center; gap: 0.6rem; margin-top: 0.6rem; }
.line { display: flex; align-items: center; gap: 0.35rem; font-family: monospace; font-size: 1.05rem; min-height: 2rem; }
.tok { padding: 0.1rem 0.5rem; border-radius: 0.4rem; background: var(--card-bg); border: 1px solid var(--card-border-subtle); color: var(--text-strong); }
.tok.new { border-color: var(--orange); background: var(--orange-bg); animation: pop 0.3s ease-out; }
.cursor { width: 2px; height: 1.2rem; background: var(--orange); animation: caret 1s steps(1) infinite; }
.cands { display: flex; gap: 0.6rem; min-height: 2.1rem; }
.cand {
  position: relative; overflow: hidden; min-width: 8rem; display: flex; justify-content: space-between; gap: 0.75rem;
  padding: 0.25rem 0.65rem; border-radius: 0.4rem; border: 1px solid var(--card-border-subtle);
  font-family: monospace; font-size: 0.85rem; color: var(--text-muted);
  background: linear-gradient(90deg, var(--orange-bg) var(--p), transparent var(--p));
  animation: appear 0.35s ease-out; transition: opacity 0.3s, border-color 0.3s, color 0.3s;
}
.cand .pct { color: var(--text-faint); }
.cand.chosen { border-color: var(--orange); color: var(--text-strong); box-shadow: 0 0 8px var(--orange-border); }
.cand.faded { opacity: 0.3; }

@keyframes appear { from { opacity: 0; transform: translateY(4px); } to { opacity: 1; transform: none; } }
@keyframes pop { from { transform: scale(0.85); opacity: 0.4; } to { transform: none; opacity: 1; } }
@keyframes caret { 50% { opacity: 0; } }
</style>
