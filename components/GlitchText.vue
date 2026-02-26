<script setup>
const props = defineProps({
  text: { type: String, required: true },
  tag: { type: String, default: 'h1' }
})
</script>

<template>
  <component :is="tag" class="glitch-wrapper">
    <span class="glitch-text" :data-text="text">{{ text }}</span>
  </component>
</template>

<style scoped>
.glitch-wrapper {
  position: relative;
  display: inline-block;
}

.glitch-text {
  position: relative;
  display: inline-block;
  font-family: 'Space Grotesk', system-ui, sans-serif;
  font-weight: 700;
  letter-spacing: -0.03em;
}

.glitch-text::before,
.glitch-text::after {
  content: attr(data-text);
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
}

.glitch-text::before {
  color: #00f0ff;
  animation: glitch-shift-1 3s infinite linear alternate-reverse;
  clip-path: polygon(0 0, 100% 0, 100% 35%, 0 35%);
  z-index: -1;
}

.glitch-text::after {
  color: #ff003c;
  animation: glitch-shift-2 2.5s infinite linear alternate-reverse;
  clip-path: polygon(0 65%, 100% 65%, 100% 100%, 0 100%);
  z-index: -1;
}

@keyframes glitch-shift-1 {
  0%, 85% { transform: translate(0); }
  86% { transform: translate(-3px, -1px); }
  88% { transform: translate(2px, 1px); }
  90% { transform: translate(-1px, 0); }
  92%, 100% { transform: translate(0); }
}

@keyframes glitch-shift-2 {
  0%, 80% { transform: translate(0); }
  81% { transform: translate(3px, 1px); }
  83% { transform: translate(-2px, -1px); }
  85% { transform: translate(1px, 0); }
  87%, 100% { transform: translate(0); }
}
</style>
