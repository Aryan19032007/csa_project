<script setup>
import { ref, onMounted } from 'vue'

const canvas = ref(null)

onMounted(() => {
  const el = canvas.value
  if (!el) return
  const ctx = el.getContext('2d')
  
  const init = () => {
    const W = el.width = el.offsetWidth * 2
    const H = el.height = el.offsetHeight * 2
    if (W === 0 || H === 0) return false
    ctx.scale(2, 2)
    return true
  }

  if (!init()) {
    // Retry once if initially 0
    setTimeout(() => init(), 100)
  }

  const w = () => el.width / 2
  const h = () => el.height / 2

  const nodes = []
  const count = 40
  for (let i = 0; i < count; i++) {
    nodes.push({
      x: Math.random() * (el.offsetWidth || 800),
      y: Math.random() * (el.offsetHeight || 600),
      vx: (Math.random() - 0.5) * 0.3,
      vy: (Math.random() - 0.5) * 0.3,
      r: Math.random() * 1.5 + 0.5
    })
  }

  function draw() {
    const width = w()
    const height = h()
    if (width === 0) {
      requestAnimationFrame(draw)
      return
    }

    ctx.fillStyle = '#050508'
    ctx.fillRect(0, 0, width, height)

    // Draw connections
    for (let i = 0; i < count; i++) {
      for (let j = i + 1; j < count; j++) {
        const dx = nodes[i].x - nodes[j].x
        const dy = nodes[i].y - nodes[j].y
        const dist = Math.sqrt(dx * dx + dy * dy)
        if (dist < 120) {
          const alpha = (1 - dist / 120) * 0.15
          ctx.strokeStyle = `rgba(0, 240, 255, ${alpha})`
          ctx.lineWidth = 0.5
          ctx.beginPath()
          ctx.moveTo(nodes[i].x, nodes[i].y)
          ctx.lineTo(nodes[j].x, nodes[j].y)
          ctx.stroke()
        }
      }
    }

    // Draw nodes
    for (const n of nodes) {
      ctx.fillStyle = 'rgba(0, 240, 255, 0.4)'
      ctx.beginPath()
      ctx.arc(n.x, n.y, n.r, 0, Math.PI * 2)
      ctx.fill()

      // Move
      n.x += n.vx
      n.y += n.vy
      if (n.x < 0 || n.x > width) n.vx *= -1
      if (n.y < 0 || n.y > height) n.vy *= -1
    }

    requestAnimationFrame(draw)
  }
  draw()
})
</script>

<template>
  <canvas ref="canvas" class="node-graph"></canvas>
</template>

<style scoped>
.node-graph {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 1;
  pointer-events: none;
}
</style>
