---
theme: seriph
class: relative text-center
transition: slide-left
mdc: true
duration: 35min
---

<audio id="slideSound" src="/swoosh.mp3" preload="auto"></audio>

<script setup>
import { watch } from 'vue'
import { useNav } from '@slidev/client'

const nav = useNav()

watch(
  () => nav.currentPage.value,
  () => {
    const audio = document.getElementById('slideSound')
    if (audio) {
      audio.currentTime = 0
      audio.play().catch(() => {})
    }
  }
)
</script>

<div class="absolute inset-0 z-0">
  <video
    src="/cpu.mp4"
    autoplay
    muted
    loop
    playsinline
    class="w-full h-full object-cover"
  ></video>
</div>

<div class="absolute inset-0 bg-black opacity-40 z-10"></div>

<div class="relative z-20 flex flex-col items-center justify-center h-full text-white">

  <h1 class="text-5xl font-bold text-red-500">
    Non-uniform Memory Access
  </h1>

  <h2 class="text-2xl mt-4 text-yellow-400">
    Memory design with a twist
  </h2>

  <div class="mt-6 text-orange-300">
    Presented to you by
    <br> Aryan Nagdawane
    <br> Suyash Chandel
    <br> Praveen Parakh
    <br> Het DharmendraBhai Dhinoja
  </div>

</div>
<!--
Just an introductory slide
-->

---
transition: slide-up
layout: two-cols-header
---



# Introduction

---
transition: fade
layout: two-cols-header
---

# Unit Distribution

::left::

## Unit 1

### Architecture Overview and System Model

*Covered by Aryan Nagdawane*

- Key characteristics
- NUMA system structure
- NUMA modes
- Local vs emote memory access
- Comparison with UMA

::right::

## Unit 2 

### Hardware Organisation and Interconnection

*Covered by Praveen Parakh*

- Multi-processor configuration
- Local memory controllers
- Interconnection network
- Address, data and control nodes
- Cache organisation


---
transition: slide-right
layout: two-cols-header
---

# Unit Distribution

::left::

## Unit 3

### Memory Hierarchy and Performance

*Covered by Het Dharmendrabhai Dhinoja*

- Memory hierarchy
- SRAM vs DRAM
- Memory latency difference
- Performance comparison with NUMA & UMA
- Bottlenecks

::right::

## Unit 4

### OS Support, Scheduling and Applications

*Covererd by Suyash Chandel*

- NUMA-aware Operating Systems
- Process and thread placement
- Memory allocation policies
- Role of DMA in NUMA
- Real world applications

---
transition: slide-down
---

# Workflow and Resources


---
transition: slide-down
---

# Summary
