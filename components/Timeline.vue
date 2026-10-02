<script setup>
defineProps({
  events: { type: Array, required: true },
  startClick: { type: Number, default: 1 },
})
</script>

<template>
  <div class="timeline" :style="{ gridTemplateColumns: `repeat(${events.length}, 1fr)` }">
    <div
      v-for="(event, i) in events"
      :key="event.title"
      v-click="startClick + i"
      class="event"
    >
      <div class="date">{{ event.date }}</div>
      <div class="dot" />
      <div class="card-left-orange card-md body">
        <p class="title">{{ event.title }}</p>
        <p v-if="event.text" class="text">{{ event.text }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.timeline {
  display: grid;
  gap: 1rem;
  position: relative;
  align-items: stretch;
  margin-block: auto;
  margin-bottom: 6rem;
}
.event { display: flex; flex-direction: column; position: relative; }
.event::before {
  content: '';
  position: absolute;
  top: 2.1rem;
  left: -0.65rem;
  right: -0.65rem;
  height: 2px;
  background: var(--orange-border);
}
.date {
  font-family: monospace;
  font-size: 0.85rem;
  line-height: 1.3;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  color: var(--orange);
  margin-bottom: 0.5rem;
}
.dot {
  width: 0.85rem;
  height: 0.85rem;
  border-radius: 50%;
  background: var(--orange);
  margin-bottom: 0.8rem;
  position: relative;
}
.body { flex: 1; padding: 0.9rem 1rem; min-height: 6.5rem; display: flex; flex-direction: column; justify-content: center; }
.title { font-weight: 700; color: var(--text-strong); margin: 0 0 0.3rem; font-size: 1.05rem; line-height: 1.3; }
.text { margin: 0; font-size: 0.75rem; line-height: 1.4; color: var(--text-muted); }
</style>
