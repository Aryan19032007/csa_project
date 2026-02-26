<script setup>
import { ref, onMounted } from 'vue'

const el = ref(null)
const chars = '01アイウエオカキクケコサシスセソタチツテト'

onMounted(() => {
  const container = el.value
  if (!container) return

  const cols = Math.floor(container.offsetWidth / 18)
  const drops = Array(cols).fill(0)

  const canvas = document.createElement('canvas')
  canvas.width = container.offsetWidth
  canvas.height = container.offsetHeight
  canvas.style.cssText = 'position:absolute;top:0;left:0;width:100%;height:100%;'
  container.appendChild(canvas)

  const ctx = canvas.getContext('2d')

  function draw() {
    ctx.fillStyle = 'rgba(5, 5, 8, 0.08)'
    ctx.fillRect(0, 0, canvas.width, canvas.height)

    ctx.fillStyle = 'rgba(0, 240, 255, 0.12)'
    ctx.font = '14px JetBrains Mono, monospace'

    for (let i = 0; i < drops.length; i++) {
      const char = chars[Math.floor(Math.random() * chars.length)]
      ctx.fillText(char, i * 18, drops[i] * 18)

      if (drops[i] * 18 > canvas.height && Math.random() > 0.98) {
        drops[i] = 0
      }
      drops[i]++
    }
    requestAnimationFrame(draw)
  }
  draw()
})
</script>

<template>
  <div ref="el" class="matrix-bg" aria-hidden="true"></div>
</template>

<style scoped>
.matrix-bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
  pointer-events: none;
  opacity: 0.5;
}
</style>
