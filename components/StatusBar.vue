<script setup>
const props = defineProps({
  progress: { type: Number, default: 0 }
})
</script>

<template>
  <div class="status-bar">
    <div class="status-inner">
      <span class="status-dot"></span>
      <span class="status-label">SYS.ACTIVE</span>
      <span class="status-sep">|</span>
      <span class="status-value">NUMA_PRESENTATION v1.0</span>
      <span class="status-sep">|</span>
      <span class="status-value">MEM.OK</span>
    </div>
    <div class="status-right">
      <span class="status-value">NODE_COUNT: 4</span>
      <span class="status-sep">|</span>
      <span class="blink">_</span>
    </div>
  </div>
</template>

<style scoped>
.status-bar {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  height: 28px;
  background: rgba(10, 10, 16, 0.9);
  border-top: 1px solid rgba(0, 240, 255, 0.1);
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 24px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.55rem;
  letter-spacing: 0.1em;
  color: rgba(0, 240, 255, 0.35);
  z-index: 20;
}

.status-inner, .status-right {
  display: flex;
  align-items: center;
  gap: 8px;
}

.status-dot {
  width: 5px;
  height: 5px;
  border-radius: 50%;
  background: #00f0ff;
  box-shadow: 0 0 6px rgba(0, 240, 255, 0.6);
  animation: dot-pulse 2s ease-in-out infinite;
}

.status-sep {
  color: rgba(0, 240, 255, 0.15);
}

.blink {
  animation: cursor-blink 1s step-end infinite;
}

@keyframes dot-pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.3; }
}

@keyframes cursor-blink {
  0%, 50% { opacity: 1; }
  51%, 100% { opacity: 0; }
}
</style>
