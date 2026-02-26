---
theme: seriph
class: relative text-center
transition: slide-left
mdc: true
duration: 35min
---
# Introduction

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

<!-- Background Video -->
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

<!-- Dark Overlay -->
<div class="absolute inset-0 bg-black opacity-40 z-10"></div>

<!-- Text Content -->
<div class="relative z-20 flex flex-col justify-center items-center h-full">

  <h1 style="color:Red;">Non-uniform Memory Access</h1>

  <h2 style="color:yellow">Memory design with a twist</h2>

  <div style="color:orange;">
    <br>Presented to you by~
    <br>•Aryan Nagdawane
    <br>•Suyash Chandel
    <br>•Praveen Parakh
    <br>•Het Dharmendrabhai Dhinoja
  </div>

  <div
    style="color:pink;"
    @click="$slidev.nav.next"
    class="mt-12 py-1 cursor-pointer"
    hover:bg="white op-10"
  >
    Let's see what its all about <carbon:arrow-right />
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

::left::

### What is NUMA?

NUMA stands for Non-Uniform Memory Access.

- Memory architecture used in multiprocessors, where access time depends on memory location

- Based on fact that processor can access own local memory faster than non-local memory

- Composed of 'nodes', each with core(s) and local memory, interconnected with each other

![](https://t1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/7ygK/image/ORbE4zzDNbyYYLUS2hJgbRsTpIc.png)


::right::

#[](https://t1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/7ygK/image/ORbE4zzDNbyYYLUS2hJgbRsTpIc.png)

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
layout: two-cols
---

::left::

## Workflow

Topics to be covered in order:
- Prerequisite: Understanding of basic CSA and virtual memory concepts
- Introduction to parallelism
- Shortcomings of traditional UMA
- Architecture behind NUMA
- Memory placement policies
- Possible optimizations
- Performance impacts
- Applications in systems 

::right::

## References

- Thomas, Gael. "Non uniform memory access", Universite Paris-Saclay. https://cs.ip-paris.fr/courses/chps/paam/cours/05-numa.pdf
- Lamater, Christopher. "NUMA (Non-Uniform Memory Access): An Overview", ResearchGate. https://www.researchgate.net/publication/261849905_NUMA_Non-Uniform_Memory_Access_An_Overview
- Unknown Author(s). "numa(7) - Linux manual page", Linux/UNIX system programming training. https://man7.org/linux/man-pages/man7/numa.7.html
- van Riel, Rik. "Automatic NUMA Balancing", Red Hat. https://events.static.linuxfound.org/sites/events/files/slides/summit2014_riel_chegu_w_0340_automatic_numa_balancing_0.pdf

<style>
  .two-cols-header {
    column-gap: 30px;
  }
</style>

---
transition: slide-down
---

# Summary
