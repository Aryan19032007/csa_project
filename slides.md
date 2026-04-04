---
theme: none
title: Our Csa Project :D
info: |
  ## Slidev Starter Template
  Presentation slides for mw

  Learn more at [Sli.dev](https://sli.dev)
drawings:
  persist: false
transition: slide-left
mdc: true
# duration: 35min
fonts:
  sans: "Playfair Display, serif"
  mono: "JetBrains Mono"
---

---
layout: default
---

# Video Player Test

<div class="w-120 h-80 mx-auto border border-gray-500/30 rounded-lg overflow-hidden shadow-xl">
  <CustomVideoPlayer 
    controls 
    :pause="[1, 1, 1]" 
    autoplay 
    src="https://vjs.zencdn.net/v/oceans.mp4"
  />
</div>

<div class="mt-4 text-center text-sm opacity-50">
  This video should pause at 1s, 2s, and 3s. Press Space or Click to advance.
</div>

---
layout: end
---

