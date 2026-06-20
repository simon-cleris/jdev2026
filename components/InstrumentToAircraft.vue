<template>
  <div class="layout">
    <div class="instruments">
      <div class="instrument-card" v-for="inst in instruments" :key="inst.src">
        <div class="instrument-label">{{ inst.label }}</div>
        <img :src="inst.src" :alt="inst.label" class="instrument-img" />
      </div>
    </div>

<div class="aircraft-side">
      <img src="/assets/SAFIRE-1.jpg" alt="Safire" class="aircraft-img" />
      <div class="aircraft-label">Safire</div>
    </div>
  </div>
</template>

<script setup>
const instruments = [
  { src: '/assets/minio3.jpg', label: 'Minio3' },
  { src: '/assets/package1.jpg', label: 'Package 1' },
]
</script>

<style scoped>
.layout {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 3rem;
  width: 100%;
  height: 100%;
}

.instruments {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  align-items: flex-end;
}

.instrument-card {
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 0.75rem;
}

.instrument-img {
  width: 200px;
  height: 130px;
  object-fit: cover;
  border-radius: 0.5rem;
  border: 2px solid rgba(255, 255, 255, 0.1);
}

.instrument-label {
  font-size: 0.85rem;
  color: var(--text-faint);
  white-space: nowrap;
}

.aircraft-side {
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 0.75rem;
}

.aircraft-img {
  width: 360px;
  height: 260px;
  object-fit: cover;
  border-radius: 0.75rem;
  border: 2px solid rgba(249, 115, 22, 0.3);
  box-shadow: 0 0 24px rgba(249, 115, 22, 0.15);
}

.aircraft-label {
  font-size: 0.85rem;
  color: var(--text-faint);
  white-space: nowrap;
}
</style>
