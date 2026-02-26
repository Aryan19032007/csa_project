---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://etimg.etb2bimg.com/photo/109156591.cms
# some information about your slides (markdown enabled)
title: Our Csa Project :D
info: |
  ## Slidev Starter Template
  Presentation slides for mw

  Learn more at [Sli.dev](https://sli.dev)
# apply UnoCSS classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# duration of the presentation
duration: 35min
---

<h1 style="color:Red;">Non-uniform Memory Access</h1>

<h2 style="color:yellow">Memory design with a twist</h2>

<div style="color:orange;">
  <br>Presented to you by~
  
<br>•Aryan Nagdawane<br>•Suyash Chandel<br>•Praveen Parakh<br>•Het DharmendraBhai Dhinoja
</div>



<div style="color:pink;" @click="$slidev.nav.next" class="mt-12 py-1" hover:bg="white op-10">
  Let's see what its all about<carbon:arrow-right />
</div>


<!--
Just an introductory slide
-->

---
transition: slide-up
---

# Aim and Intent

<audio id="transitionSound" src="/swoosh.mp3" style="display:none"></audio>


<script setup>
import { watch } from 'vue'
import { useNav } from '@slidev/client'

const nav = useNav()

watch(
  () => nav.currentPage.value,
  (page) => {
    if (page === 2) {
      const audio = document.getElementById('transitionSound')
      if (audio) {
        audio.currentTime = 0
        audio.play().catch(() => {})
      }
    }
  }
)
</script>

---
transition: fade
---

# Topic Distribution



---
transition: fade
---

# Topic Distribution

---
transition: slide-right
---

# Workflow and Resources


---
transition: slide-down
---

# Summary
