<script setup lang="ts">
import { computed, onMounted, ref, watch } from 'vue'
import { useNav } from '@slidev/client'

const props = defineProps<{
  src?: string
  autoplay?: boolean | 'once'
  autoreset?: 'slide' | 'click'
  poster?: string
  printPoster?: string
  timestamp?: string | number
  printTimestamp?: string | number | 'last'
  controls?: boolean
  pause?: (number | 'end')[]
  muted?: boolean
}>()

const video = ref<HTMLVideoElement>()
const { clicks, currentSlideNo, isPrintMode } = useNav()
const playedOnce = ref(false)

// Determine if we should be playing or just showing a static frame
const isInteractive = computed(() => !isPrintMode.value)

// Parse pause timestamps into absolute stop points
const stopPoints = computed(() => {
  if (!props.pause) return []
  const points: (number | 'end')[] = []
  let cumulative = 0
  for (const p of props.pause) {
    if (p === 'end') {
      points.push('end')
    } else {
      cumulative += p
      points.push(cumulative)
    }
  }
  return points
})

const currentPauseIndex = ref(0)

// Monitor video time to pause at stop points
function handleTimeUpdate() {
  if (!video.value || currentPauseIndex.value >= stopPoints.value.length) return

  const nextStop = stopPoints.value[currentPauseIndex.value]
  if (typeof nextStop === 'number' && video.value.currentTime >= nextStop) {
    video.value.pause()
    video.value.currentTime = nextStop // Snap to exact point
    currentPauseIndex.value++
  }
}

// Play the next segment
async function playNext() {
  if (!video.value) return
  
  try {
    await video.value.play()
  } catch (err) {
    console.error("Video play failed:", err)
  }
}

// Watch for click changes to advance video
watch(clicks, (newClicks, oldClicks) => {
  if (newClicks > oldClicks) {
    playNext()
  }
})

// Handle slide entry/exit
watch(currentSlideNo, (newVal, oldVal) => {
  if (!video.value) return

  // Reset logic
  if (props.autoreset === 'slide' || (props.autoreset === 'click' && newVal !== oldVal)) {
    video.value.pause()
    video.value.currentTime = Number(props.timestamp || 0)
    currentPauseIndex.value = 0
  }
})

onMounted(() => {
  if (video.value && props.timestamp) {
    video.value.currentTime = Number(props.timestamp)
  }

  // Initial autoplay logic
  if (props.autoplay && !isPrintMode.value) {
    if (props.autoplay === 'once' && playedOnce.value) return
    playNext()
    playedOnce.value = true
  }
})

function onEnded() {
  if (props.autoreset === 'slide' || props.autoreset === 'click') {
    currentPauseIndex.value = 0
  }
}
</script>

<template>
  <div class="custom-video-container" :class="{ 'is-print': isPrintMode }">
    <!-- 
      Register clicks in Slidev. Each element with v-click tells Slidev 
      that the slide has an additional 'step' before moving to the next slide.
    -->
    <div v-for="i in (pause?.length || 0)" :key="i" v-click class="hidden"></div>

    <video
      ref="video"
      :src="src"
      :poster="isPrintMode ? (printPoster || poster) : poster"
      :controls="controls && isInteractive"
      :muted="muted || autoplay !== undefined"
      playsinline
      class="w-full h-full object-cover"
      @timeupdate="handleTimeUpdate"
      @ended="onEnded"
    >
      <slot />
    </video>
  </div>
</template>

<style scoped>
.custom-video-container {
  position: relative;
  width: 100%;
  height: 100%;
  overflow: hidden;
  background: black;
}

video {
  display: block;
}

.hidden {
  display: none;
}

.is-print video {
  pointer-events: none;
}
</style>
