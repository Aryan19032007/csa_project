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



<!--
Just an introductory slide
-->

---
transition: slide-up

layout: two-cols-header
---

# Introduction

<audio id="transitionSound" src="/swoosh.mp3" style="display:none"></audio>

::left::

### What is NUMA?

NUMA stands for Non-Uniform Memory Access.

- Memory architecture used in multiprocessors, where access time depends on memory location

- Based on fact that processor can access own local memory faster than non-local memory

- Composed of 'nodes', each with core(s) and local memory, interconnected with each other

<img src="https://t1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/7ygK/image/ORbE4zzDNbyYYLUS2hJgbRsTpIc.png" class="h-50 mx-auto rounded shadow-lg" />


::right::


### Why we chose it?

- Reasonably easy to grasp understanding of
- Clever application of parallelism
- Extensively used in modern OSes

### What are we aiming for?

To understand and explain:

- How NUMA works
- What the benefits and drawbacks of how NUMA works
- How modern OSes implement NUMA

<style>
  .two-cols-header {
    column-gap: 30px;
  }
</style>

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
layout: two-cols-header
---

# Unit Distribution

::left::

## Unit 1

### Architecture Overview and System Model

*Covered by Aryan Nagdawade*

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
