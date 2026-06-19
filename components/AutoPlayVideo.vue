<script setup>
import { ref } from 'vue'
import { onSlideEnter } from '@slidev/client'

const props = defineProps({ src: String })
const video = ref(null)

onSlideEnter(() => {
  if (video.value) {
    video.value.currentTime = 0
    video.value.play()
  }
})
</script>

<template>
  <video
    ref="video"
    :src="src"
    muted
    playsinline
    style="width: 100%; height: 100%; max-height: 100%; object-fit: contain; border-radius: 0.75rem;"
  />
</template>
