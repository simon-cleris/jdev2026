<script setup>
import { useNav } from '@slidev/client'
import { sections } from './sections.js'

const { currentPage, total } = useNav()

function state(s) {
  if (currentPage.value > s.to) return 'done'
  if (currentPage.value >= s.from) return 'active'
  return 'todo'
}
</script>

<template>
  <div class="logos-bar">
    <span class="page-number">{{ currentPage }} / {{ total }}</span>
    <nav class="sections" :class="{ hidden: currentPage <= 2 || currentPage >= total }">
      <span v-for="(s, i) in sections" :key="s.title" class="chip" :class="state(s)">
        <b>{{ String(i + 1).padStart(2, '0') }}</b>
        <span v-if="state(s) === 'active'">{{ s.short }}</span>
      </span>
    </nav>
    <img src="./assets/laero.jpg" alt="LAERO" />
    <img src="./assets/logo_omp.png" alt="OMP" />
    <img src="./assets/logo_utoulouse.png" alt="Université de Toulouse" />
    <img src="./assets/LOGO_CNRS_BLEU.png" alt="CNRS" />
    <span class="ird">
      <img src="./assets/logoIRD_Horizontal_Baseline_FR_Noir.png" alt="IRD" />
    </span>
  </div>
</template>

<style scoped>
.logos-bar {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  height: 24px;
  background: rgba(255, 255, 255, 0.92);
  display: flex;
  align-items: center;
  justify-content: right;
  gap: 28px;
  padding: 0 3.5rem;
  z-index: 100;
}

.sections {
  display: flex;
  align-items: center;
  gap: 4px;
  margin-right: auto;
}

.chip {
  display: flex;
  align-items: center;
  gap: 5px;
  padding: 1px 5px;
  border-radius: 3px;
  font-family: monospace;
  font-size: 10px;
  color: #133F85;
  opacity: 0.35;
}

.chip b {
  font-weight: 700;
}

.chip.done {
  opacity: 0.7;
}

.chip.active {
  opacity: 1;
  background: #133F85;
  color: #ffffff;
}

.sections.hidden {
  visibility: hidden;
}

.page-number {
  min-width: 4rem;
  font-size: 11px;
  font-family: monospace;
  color: #133F85;
  opacity: 0.7;
}

.logos-bar > img {
  height: 17px;
  width: auto;
  object-fit: contain;
}

/* Logo IRD : l'image source (3508x2481) a de grandes marges, on recadre
   sur la zone utile (1645x360 à partir de 933,1060) à hauteur de 20px. */
.logos-bar .ird {
  display: block;
  width: 77px;
  height: 17px;
  overflow: hidden;
}

.logos-bar .ird img {
  display: block;
  max-width: none;
  width: 165px;
  margin: -50px 0 0 -43.9px;
}
</style>
