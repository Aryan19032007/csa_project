<script setup>
import { ref, onMounted } from 'vue'

const canvas = ref(null)

onMounted(() => {
  const el = canvas.value
  if (!el) return
  const ctx = el.getContext('2d')
  
  const resize = () => {
    const W = el.width = el.offsetWidth * 2
    const H = el.height = el.offsetHeight * 2
    if (W === 0 || H === 0) return false
    ctx.scale(2, 2)
    return true
  }
  
  if (!resize()) {
    setTimeout(() => resize(), 100)
  }
  
  const w = () => el.width / 2
  const h = () => el.height / 2
  
  let t = 0
  
  function draw() {
    const W = w()
    const H = h()
    if (W === 0) {
      requestAnimationFrame(draw)
      return
    }

    ctx.fillStyle = '#050508'
    ctx.fillRect(0, 0, W, H)
    
    // Orbiting rings
    const cx = W / 2
    const cy = H / 2
    
    for (let ring = 0; ring < 3; ring++) {
      const radius = 60 + ring * 45
      const speed = 0.008 + ring * 0.003
      const alpha = 0.06 - ring * 0.015
      
      ctx.strokeStyle = `rgba(0, 240, 255, ${alpha})`
      ctx.lineWidth = 0.5
      ctx.beginPath()
      ctx.ellipse(cx, cy, radius, radius * 0.35, t * speed, 0, Math.PI * 2)
      ctx.stroke()
      
      // Orbiting dot
      const dotAngle = t * speed * 3 + ring * 2
      const dx = cx + Math.cos(dotAngle) * radius
      const dy = cy + Math.sin(dotAngle) * radius * 0.35
      
      ctx.fillStyle = ring === 0 ? 'rgba(0, 240, 255, 0.6)' : ring === 1 ? 'rgba(255, 0, 60, 0.5)' : 'rgba(180, 0, 255, 0.5)'
      ctx.beginPath()
      ctx.arc(dx, dy, 2, 0, Math.PI * 2)
      ctx.fill()
    }
    
    // Center core
    const coreGlow = 0.3 + Math.sin(t * 0.02) * 0.1
    const gradient = ctx.createRadialGradient(cx, cy, 0, cx, cy, 30)
    gradient.addColorStop(0, `rgba(0, 240, 255, ${coreGlow})`)
    gradient.addColorStop(1, 'rgba(0, 240, 255, 0)')
    ctx.fillStyle = gradient
    ctx.beginPath()
    ctx.arc(cx, cy, 30, 0, Math.PI * 2)
    ctx.fill()
    
    ctx.fillStyle = 'rgba(0, 240, 255, 0.8)'
    ctx.beginPath()
    ctx.arc(cx, cy, 3, 0, Math.PI * 2)
    ctx.fill()
    
    t++
    requestAnimationFrame(draw)
  }
  draw()
})
</script>

<template>
  <canvas ref="canvas" class="orbit-vis"></canvas>
</template>

<style scoped>
.orbit-vis {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 1;
  pointer-events: none;
}
</style>
