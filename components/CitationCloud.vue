<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'

const props = defineProps({
  citations: { type: Array, default: () => [] },
  interval: { type: Number, default: 7000 },
  title: { type: String, default: '' },
  author: { type: String, default: '' },
  affiliation: { type: String, default: '' },
})

const texts = computed(() =>
  props.citations.map(c => (typeof c === 'string' ? c : c.text))
)

const W = ref(0)
const H = ref(0)
const containerRef = ref(null)
const cloudAreaRef = ref(null)

// Each particle: position, velocity, citation index
const particles = ref([])
const activeIdx = ref(null)
let animFrame = null
let highlightTimer = null

function initParticles() {
  const w = W.value
  const h = H.value
  particles.value = texts.value.map((_, i) => ({
    id: i,
    x: Math.random() * w,
    y: Math.random() * h,
    vx: (Math.random() - 0.5) * 0.90,
    vy: (Math.random() - 0.5) * 0.90,
  }))
}

function tick() {
  const w = W.value
  const h = H.value
  for (const p of particles.value) {
    if (p.id === activeIdx.value) continue
    p.x += p.vx
    p.y += p.vy
    if (p.x < 0) { p.x = 0; p.vx *= -1 }
    if (p.x > w) { p.x = w; p.vx *= -1 }
    if (p.y < 0) { p.y = 0; p.vy *= -1 }
    if (p.y > h) { p.y = h; p.vy *= -1 }
  }
  animFrame = requestAnimationFrame(tick)
}

function pickNext() {
  const next = (activeIdx.value === null ? 0 : (activeIdx.value + 1) % texts.value.length)
  activeIdx.value = next
}

onMounted(() => {
  const area = cloudAreaRef.value ?? containerRef.value
  W.value = area.offsetWidth
  H.value = area.offsetHeight
  initParticles()
  tick()
  pickNext()
  highlightTimer = setInterval(pickNext, props.interval)
})

onUnmounted(() => {
  cancelAnimationFrame(animFrame)
  clearInterval(highlightTimer)
})

function particleStyle(p) {
  const isActive = p.id === activeIdx.value
  if (isActive) {
    return {
      left: '50%',
      top: '50%',
      transform: 'translate(-50%, -50%)',
      transition: 'left 0.9s cubic-bezier(0.16,1,0.3,1), top 0.9s cubic-bezier(0.16,1,0.3,1), transform 0.9s cubic-bezier(0.16,1,0.3,1)',
      zIndex: 10,
    }
  }
  return {
    left: p.x + 'px',
    top: p.y + 'px',
    transform: 'translate(-50%, -50%)',
    transition: 'left 0.9s cubic-bezier(0.16,1,0.3,1), top 0.9s cubic-bezier(0.16,1,0.3,1)',
    zIndex: 1,
  }
}
</script>

<template>
  <div ref="containerRef" class="cloud-root">
    <div v-if="title" class="title-banner">
      <span class="title-text">{{ title }}</span>
    </div>
    <div ref="cloudAreaRef" class="cloud-area">
      <div
        v-for="p in particles"
        :key="p.id"
        class="particle"
        :class="{ active: p.id === activeIdx }"
        :style="particleStyle(p)"
      >
        <span class="p-text">"{{ texts[p.id] }}"</span>
      </div>
    </div>
    <div v-if="author" class="author">
      <span class="author-name">{{ author }}</span>
      <span v-if="affiliation" class="author-affiliation">{{ affiliation }}</span>
    </div>
  </div>
</template>

<style scoped>
.cloud-root {
  position: absolute;
  inset: 0;
  overflow: hidden;
  background: var(--bg);
  display: flex;
  flex-direction: column;
}

.title-banner {
  flex-shrink: 0;
  height: 100px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #ffffff;
  padding: 0 3rem;
}

.title-text {
  font-size: 1.8rem;
  font-weight: 700;
  color: var(--navy);
  text-align: center;
  letter-spacing: -0.02em;
  line-height: 1.2;
}

.cloud-area {
  position: relative;
  flex: 1;
  overflow: hidden;
}

.author {
  position: absolute;
  left: 2rem;
  bottom: 2.25rem;
  z-index: 20;
  display: flex;
  flex-direction: column;
  gap: 0.15rem;
  padding-left: 0.75rem;
  border-left: 3px solid var(--orange);
}

.author-name {
  font-size: 0.95rem;
  font-weight: 700;
  color: #ffffff;
}

.author-affiliation {
  font-size: 0.75rem;
  color: var(--text-muted);
}

.particle {
  position: absolute;
  pointer-events: none;
  user-select: none;
  font-style: italic;
  line-height: 1.35;
  width: 300px;
  text-align: center;
}

.p-text {
  font-size: 0.6rem;
  color: rgba(255, 255, 255, 0.15);
  transition: color 0.9s ease, opacity 0.9s ease;
  display: block;
}

.particle.active .p-text {
  font-size: 1.0rem;
  color: #f1f5f9;
  display: block;
}


.particle.active {
  width: 640px;
  max-width: 640px;
  text-align: center;
}

.particle.active::before {
  content: '';
  position: absolute;
  inset: -1.5rem -2rem -1.5rem -2.25rem;
  background: rgba(0, 0, 0, 0.55);
  border-left: 3px solid var(--orange);
  border-radius: 4px;
  backdrop-filter: blur(6px);
  z-index: -1;
}
</style>
