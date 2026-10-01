<script setup>
const stops = [
  { title: 'Vibe Coding', color: '#f87171', point: '« Ça a l\'air de marcher ? »' },
  { title: 'Assisté et structuré', color: '#e2e8f0', point: 'Tests manuels' },
  { title: 'Agentic Engineering', color: '#3EC1F0', point: 'Specs + évaluations automatiques + CI/CD' },
]
</script>

<template>
  <div class="spectrum">
    <div class="stops">
      <div v-for="(s, i) in stops" :key="s.title" v-click="i + 1" class="stop">
        <div class="stop-title" :style="{ color: s.color }">{{ s.title }}</div>
        <p class="point">{{ s.point }}</p>
        <div class="tick" :style="{ background: s.color }" />
      </div>
    </div>

    <div class="bar" />
    <div class="axis">
      <span>Moins de structure, plus de vitesse</span>
      <span>Plus de structure, plus de fiabilité</span>
    </div>
  </div>
</template>

<style scoped>
.spectrum {
  display: flex;
  flex-direction: column;
  justify-content: center;
  flex: 1;
  gap: 0.75rem;
}
.stops {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}
.stop {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 0.4rem;
}
.stop-title {
  font-size: 1.25rem;
  font-weight: 700;
}
.point {
  margin: 0;
  font-size: 1rem;
  color: var(--text-muted);
}
.tick {
  width: 3px;
  height: 2rem;
  margin-top: auto;
}
.bar {
  height: 1.5rem;
  border-radius: 999px;
  border: 1px solid var(--navy-border);
  background: linear-gradient(90deg, #ef4444, #8b5a9e 50%, #3EC1F0);
}
.axis {
  display: flex;
  justify-content: space-between;
  font-size: 0.75rem;
  color: var(--text-faint);
}
</style>
