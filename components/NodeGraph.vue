<script setup>
import { ref, onMounted } from 'vue'

const canvas = ref(null)

onMounted(() => {
  const el = canvas.value
  if (!el) return
  const ctx = el.getContext('2d')
  const W = el.width = el.offsetWidth * 2
  const H = el.height = el.offsetHeight * 2
  ctx.scale(2, 2)
  const w = W / 2
  const h = H / 2

  const nodes = []
  const count = 40
  for (let i = 0; i < count; i++) {
    nodes.push({
      x: Math.random() * w,
      y: Math.random() * h,
      vx: (Math.random() - 0.5) * 0.3,
      vy: (Math.random() - 0.5) * 0.3,
      r: Math.random() * 1.5 + 0.5
    })
  }

  function draw() {
    ctx.clearRect(0, 0, w, h)

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
      if (n.x < 0 || n.x > w) n.vx *= -1
      if (n.y < 0 || n.y > h) n.vy *= -1
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
  opacity: 0.6;
  pointer-events: none;
}
</style>
