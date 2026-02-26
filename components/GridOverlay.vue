<template>
  <div class="grid-overlay" aria-hidden="true">
    <div class="grid-lines"></div>
    <div class="corner tl"></div>
    <div class="corner tr"></div>
    <div class="corner bl"></div>
    <div class="corner br"></div>
    <div class="coord-label top-label">
      <span>NUMA // CSA_PROJECT</span>
    </div>
    <div class="coord-label bottom-label">
      <span>2025.PRESENTATION</span>
    </div>
  </div>
</template>

<style scoped>
.grid-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: 10;
}

.grid-lines {
  position: absolute;
  top: 0; left: 0; right: 0; bottom: 0;
  background-image:
    linear-gradient(rgba(0, 240, 255, 0.025) 1px, transparent 1px),
    linear-gradient(90deg, rgba(0, 240, 255, 0.025) 1px, transparent 1px);
  background-size: 80px 80px;
}

.corner {
  position: absolute;
  width: 24px;
  height: 24px;
}

.corner.tl {
  top: 24px; left: 24px;
  border-top: 1.5px solid rgba(0, 240, 255, 0.25);
  border-left: 1.5px solid rgba(0, 240, 255, 0.25);
}
.corner.tr {
  top: 24px; right: 24px;
  border-top: 1.5px solid rgba(0, 240, 255, 0.25);
  border-right: 1.5px solid rgba(0, 240, 255, 0.25);
}
.corner.bl {
  bottom: 24px; left: 24px;
  border-bottom: 1.5px solid rgba(0, 240, 255, 0.25);
  border-left: 1.5px solid rgba(0, 240, 255, 0.25);
}
.corner.br {
  bottom: 24px; right: 24px;
  border-bottom: 1.5px solid rgba(0, 240, 255, 0.25);
  border-right: 1.5px solid rgba(0, 240, 255, 0.25);
}

.coord-label {
  position: absolute;
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.55rem;
  letter-spacing: 0.15em;
  color: rgba(0, 240, 255, 0.15);
  text-transform: uppercase;
}

.top-label {
  top: 28px;
  left: 56px;
}

.bottom-label {
  bottom: 28px;
  right: 56px;
}
</style>
