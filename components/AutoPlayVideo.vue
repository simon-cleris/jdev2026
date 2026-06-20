<script setup>
import { ref, computed } from 'vue'
import { onSlideEnter, onSlideLeave } from '@slidev/client'

const props = defineProps({ src: String })
const resolvedSrc = computed(() => import.meta.env.BASE_URL.replace(/\/$/, '') + props.src)
const video = ref(null)

onSlideEnter(() => {
  if (video.value) {
    video.value.currentTime = 0
    video.value.play()
  }
})

onSlideLeave(() => {
  if (video.value) {
    video.value.pause()
    video.value.currentTime = 0
  }
})
</script>

<template>
  <video
    ref="video"
    :src="resolvedSrc"
    playsinline
    style="width: 100%; height: 100%; max-height: 100%; object-fit: contain; border-radius: 0.75rem;"
  />
</template>
