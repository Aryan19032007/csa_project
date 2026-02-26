---
theme: none
title: Our Csa Project :D
info: |
  ## Slidev Starter Template
  Presentation slides for mw

  Learn more at [Sli.dev](https://sli.dev)
drawings:
  persist: false
transition: fade
mdc: true
duration: 35min
fonts:
  sans: 'Playfair Display, serif'
  mono: 'JetBrains Mono'
---

<div style="position: absolute; top: 0; left: 0; right: 0; bottom: 0; overflow: hidden; background: #050508; z-index: 10;">
<NodeGraph />
<div style="position: absolute; top: 0; left: 0; right: 0; bottom: 0; background: radial-gradient(ellipse at 50% 40%, rgba(0,240,255,0.06) 0%, rgba(0,240,255,0) 60%); pointer-events: none;"></div>
<div style="position: absolute; top: 0; left: 0; right: 0; bottom: 0; background: radial-gradient(ellipse at 70% 80%, rgba(255,0,60,0.04) 0%, rgba(255,0,60,0) 50%); pointer-events: none;"></div>
<GridOverlay />
<div style="position: relative; z-index: 20; display: flex; flex-direction: column; justify-content: center; align-items: flex-start; height: 100%; padding: 4rem 5rem;">
<div style="font-family: 'JetBrains Mono', monospace; font-size: 0.6rem; letter-spacing: 0.25em; text-transform: uppercase; color: rgba(0,240,255,0.4); margin-bottom: 2rem;">
CSA Project // Computer System Architecture
</div>
<div style="position: relative;">
<GlitchText text="Non-uniform Memory Access" tag="h1" style="font-size: 2.8rem; font-weight: 700; color: #e8e8f0; line-height: 1.1; position: relative; z-index: 1;" />
</div>
<div style="width: 120px; height: 2px; background: linear-gradient(90deg, #00f0ff, #ff003c, transparent); margin: 2rem 0;"></div>
<div style="color: rgba(232,232,240,0.5); font-size: 0.75rem; letter-spacing: 0.02em; line-height: 2;">
Presented to you by:
</div>

<div style="color: rgba(0,240,255,0.7); font-family: 'JetBrains Mono', monospace; font-size: 0.85rem; margin-top: 0.5rem;">

- Aryan Nagdawane
- Suyash Chandel
- Praveen Parakh
- Het DharmendraBhai Dhinoja

</div>
</div>
<StatusBar />
</div>

<!--
Just an introductory slide
-->

---
transition: slide-up
---

<div style="position: absolute; top: 0; left: 0; right: 0; bottom: 0; overflow: hidden; background: #050508; z-index: 10;">
<MatrixRain />
<div style="position: absolute; top: 0; left: 0; right: 0; bottom: 0; background: radial-gradient(ellipse at 30% 50%, rgba(180,0,255,0.05) 0%, rgba(180,0,255,0) 60%); pointer-events: none;"></div>
<GridOverlay />
<div style="position: relative; z-index: 20; display: flex; flex-direction: column; height: 100%; padding: 3rem 5rem;">
<div style="display: flex; align-items: center; gap: 1rem; margin-bottom: 0.8rem;">
<div>
<div style="font-family: 'JetBrains Mono', monospace; font-size: 0.55rem; letter-spacing: 0.2em; text-transform: uppercase; color: rgba(0,240,255,0.3);">Section</div>
<div style="width: 40px; height: 1px; background: rgba(0,240,255,0.2); margin-top: 4px;"></div>
</div>
</div>
<GlitchText text="Introduction" tag="h1" style="font-size: 2.4rem; font-weight: 700; color: #e8e8f0; margin-bottom: 0.5rem;" />
<div style="width: 80px; height: 2px; background: linear-gradient(90deg, #b400ff, #00f0ff, transparent); margin: 1rem 0;"></div>

<div style="display: grid; grid-template-columns: 1fr 1px 1fr; gap: 2.5rem; flex: 1; overflow: hidden;">
<div style="position: relative; overflow-y: auto;">
<div style="position: absolute; top: -8px; left: 0; right: 0; height: 2px; background: linear-gradient(90deg, #00f0ff, transparent);"></div>
<div style="padding-top: 1.2rem;">
<div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.6rem;">
<span class="tag tag-cyan">Overview</span>
</div>
<h2 style="font-family: var(--slidev-font-sans); font-size: 1.1rem; font-weight: 600; color: rgba(0,240,255,0.9); margin-bottom: 0.5rem;">What is NUMA?</h2>
<div style="color: var(--c-text-dim); font-size: 0.8rem; margin-bottom: 0.8rem;">NUMA stands for Non-Uniform Memory Access.</div>
<ul class="styled-list">
<li>Memory architecture used in multiprocessors, where access time depends on memory location</li>
<li>Based on fact that processor can access own local memory faster than non-local memory</li>
<li>Composed of 'nodes', each with core(s) and local memory, interconnected with each other</li>
</ul>
<div style="margin-top: 0.8rem;">
<img src="https://t1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/7ygK/image/ORbE4zzDNbyYYLUS2hJgbRsTpIc.png" style="max-width: 100%; max-height: 140px; object-fit: contain; border: 1px solid rgba(0,240,255,0.1); border-radius: 2px;" />
</div>
</div>
</div>
<div style="background: linear-gradient(180deg, rgba(0,240,255,0.15), rgba(255,0,60,0.15), transparent); width: 1px;"></div>
<div style="position: relative; overflow-y: auto;">
<div style="position: absolute; top: -8px; left: 0; right: 0; height: 2px; background: linear-gradient(90deg, #ff003c, transparent);"></div>
<div style="padding-top: 1.2rem;">
<div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.6rem;">
<span class="tag tag-red">Motivation</span>
</div>
<h2 style="font-family: var(--slidev-font-sans); font-size: 1.1rem; font-weight: 600; color: rgba(255,0,60,0.9); margin-bottom: 0.5rem;">Why we chose it?</h2>
<ul class="styled-list">
<li>Reasonably easy to grasp understanding of</li>
<li>Clever application of parallelism</li>
<li>Extensively used in modern OSes</li>
</ul>
<h2 style="font-family: var(--slidev-font-sans); font-size: 1.1rem; font-weight: 600; color: rgba(255,0,60,0.9); margin-bottom: 0.5rem; margin-top: 1.5rem;">What are we aiming for?</h2>
<div style="color: var(--c-text-dim); font-size: 0.8rem; margin-bottom: 0.6rem;">To understand and explain:</div>
<ul class="styled-list">
<li>How NUMA works</li>
<li>What the benefits and drawbacks of how NUMA works</li>
<li>How modern OSes implement NUMA</li>
</ul>
</div>
</div>
</div>
</div>
<TransitionSound :page="2" src="/swoosh.mp3" />
<StatusBar />
</div>

---
transition: fade
---

<div class="absolute inset-0 overflow-hidden" style="background: #050508; z-index: 10;">
<div class="absolute inset-0" style="background: radial-gradient(ellipse at 20% 30%, rgba(0,240,255,0.04) 0%, transparent 50%), radial-gradient(ellipse at 80% 70%, rgba(255,0,60,0.04) 0%, transparent 50%);"></div>
<GridOverlay />
<div class="relative z-20 flex flex-col h-full" style="padding: 3rem 5rem;">
<div style="display: flex; align-items: center; gap: 1rem; margin-bottom: 0.8rem;">
<div>
<div style="font-family: 'JetBrains Mono', monospace; font-size: 0.55rem; letter-spacing: 0.2em; text-transform: uppercase; color: rgba(0,240,255,0.3);">Distribution</div>
</div>
</div>
<h1 style="font-family: var(--slidev-font-sans); font-size: 2rem; font-weight: 700; color: #e8e8f0; letter-spacing: -0.03em; margin-bottom: 0.3rem;">Unit Distribution</h1>
<div style="width: 100%; height: 1px; background: linear-gradient(90deg, rgba(0,240,255,0.2), rgba(255,0,60,0.2), transparent); margin-bottom: 2rem;"></div>
<div style="display: grid; grid-template-columns: 1fr 1px 1fr; gap: 2.5rem; flex: 1;">
<div style="position: relative;">
<div style="position: absolute; top: -8px; left: 0; right: 0; height: 2px; background: linear-gradient(90deg, #00f0ff, transparent);"></div>
<div style="padding-top: 1.5rem;">
<div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.8rem;">
<span class="tag tag-cyan">Unit 1</span>
</div>
<h2 style="font-family: var(--slidev-font-sans); font-size: 1.1rem; font-weight: 600; color: rgba(0,240,255,0.9); margin-bottom: 0.3rem;">Architecture Overview and System Model</h2>
<div style="font-family: 'JetBrains Mono', monospace; font-size: 0.65rem; color: rgba(0,240,255,0.35); letter-spacing: 0.05em; margin-bottom: 1.2rem; font-style: italic;">Covered by Aryan Nagdawane</div>
<ul class="styled-list">
<li>Key characteristics</li>
<li>NUMA system structure</li>
<li>NUMA modes</li>
<li>Local vs emote memory access</li>
<li>Comparison with UMA</li>
</ul>
</div>
</div>
<div style="background: linear-gradient(180deg, rgba(0,240,255,0.15), rgba(255,0,60,0.15), transparent); width: 1px;"></div>
<div style="position: relative;">
<div style="position: absolute; top: -8px; left: 0; right: 0; height: 2px; background: linear-gradient(90deg, #ff003c, transparent);"></div>
<div style="padding-top: 1.5rem;">
<div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.8rem;">
<span class="tag tag-red">Unit 2</span>
</div>
<h2 style="font-family: var(--slidev-font-sans); font-size: 1.1rem; font-weight: 600; color: rgba(255,0,60,0.9); margin-bottom: 0.3rem;">Hardware Organisation and Interconnection</h2>
<div style="font-family: 'JetBrains Mono', monospace; font-size: 0.65rem; color: rgba(255,0,60,0.35); letter-spacing: 0.05em; margin-bottom: 1.2rem; font-style: italic;">Covered by Praveen Parakh</div>
<ul class="styled-list">
<li>Multi-processor configuration</li>
<li>Local memory controllers</li>
<li>Interconnection network</li>
<li>Address, data and control nodes</li>
<li>Cache organisation</li>
</ul>
</div>
</div>
</div>
</div>
<StatusBar />
</div>

---
transition: slide-left
---

<div class="absolute inset-0 overflow-hidden" style="background: #050508; z-index: 10;">
<div class="absolute inset-0" style="background: radial-gradient(ellipse at 80% 30%, rgba(180,0,255,0.04) 0%, transparent 50%), radial-gradient(ellipse at 20% 70%, rgba(0,240,255,0.04) 0%, transparent 50%);"></div>
<GridOverlay />
<div class="relative z-20 flex flex-col h-full" style="padding: 3rem 5rem;">
<div style="display: flex; align-items: center; gap: 1rem; margin-bottom: 0.8rem;">
<div>
<div style="font-family: 'JetBrains Mono', monospace; font-size: 0.55rem; letter-spacing: 0.2em; text-transform: uppercase; color: rgba(180,0,255,0.3);">Distribution</div>
</div>
</div>
<h1 style="font-family: var(--slidev-font-sans); font-size: 2rem; font-weight: 700; color: #e8e8f0; letter-spacing: -0.03em; margin-bottom: 0.3rem;">Unit Distribution</h1>
<div style="width: 100%; height: 1px; background: linear-gradient(90deg, rgba(180,0,255,0.2), rgba(0,240,255,0.2), transparent); margin-bottom: 2rem;"></div>
<div style="display: grid; grid-template-columns: 1fr 1px 1fr; gap: 2.5rem; flex: 1;">
<div style="position: relative;">
<div style="position: absolute; top: -8px; left: 0; right: 0; height: 2px; background: linear-gradient(90deg, #b400ff, transparent);"></div>
<div style="padding-top: 1.5rem;">
<div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.8rem;">
<span class="tag tag-purple">Unit 3</span>
</div>
<h2 style="font-family: var(--slidev-font-sans); font-size: 1.1rem; font-weight: 600; color: rgba(180,0,255,0.9); margin-bottom: 0.3rem;">Memory Hierarchy and Performance</h2>
<div style="font-family: 'JetBrains Mono', monospace; font-size: 0.65rem; color: rgba(180,0,255,0.35); letter-spacing: 0.05em; margin-bottom: 1.2rem; font-style: italic;">Covered by Het Dharmendrabhai Dhinoja</div>
<ul class="styled-list">
<li>Memory hierarchy</li>
<li>SRAM vs DRAM</li>
<li>Memory latency difference</li>
<li>Performance comparison with NUMA & UMA</li>
<li>Bottlenecks</li>
</ul>
</div>
</div>
<div style="background: linear-gradient(180deg, rgba(180,0,255,0.15), rgba(0,240,255,0.15), transparent); width: 1px;"></div>
<div style="position: relative;">
<div style="position: absolute; top: -8px; left: 0; right: 0; height: 2px; background: linear-gradient(90deg, #00f0ff, transparent);"></div>
<div style="padding-top: 1.5rem;">
<div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.8rem;">
<span class="tag tag-cyan">Unit 4</span>
</div>
<h2 style="font-family: var(--slidev-font-sans); font-size: 1.1rem; font-weight: 600; color: rgba(0,240,255,0.9); margin-bottom: 0.3rem;">OS Support, Scheduling and Applications</h2>
<div style="font-family: 'JetBrains Mono', monospace; font-size: 0.65rem; color: rgba(0,240,255,0.35); letter-spacing: 0.05em; margin-bottom: 1.2rem; font-style: italic;">Covered by Suyash Chandel</div>
<ul class="styled-list">
<li>NUMA-aware Operating Systems</li>
<li>Process and thread placement</li>
<li>Memory allocation policies</li>
<li>Role of DMA in NUMA</li>
<li>Real world applications</li>
</ul>
</div>
</div>
</div>
</div>
<StatusBar />
</div>

---
transition: slide-down
---

<div style="position: absolute; top: 0; left: 0; right: 0; bottom: 0; overflow: hidden; background: #050508; z-index: 10;">
<OrbitVis />
<div style="position: absolute; top: 0; left: 0; right: 0; bottom: 0; background: radial-gradient(ellipse at 50% 50%, rgba(0,240,255,0.05) 0%, rgba(0,240,255,0) 60%); pointer-events: none;"></div>
<GridOverlay />
<div style="position: relative; z-index: 20; display: flex; flex-direction: column; height: 100%; padding: 3rem 5rem;">
<div style="display: flex; align-items: center; gap: 1rem; margin-bottom: 0.8rem;">
<div>
<div style="font-family: 'JetBrains Mono', monospace; font-size: 0.55rem; letter-spacing: 0.2em; text-transform: uppercase; color: rgba(0,240,255,0.3);">Process</div>
<div style="width: 40px; height: 1px; background: rgba(0,240,255,0.2); margin-top: 4px;"></div>
</div>
</div>
<GlitchText text="Workflow and Resources" tag="h1" style="font-size: 2.4rem; font-weight: 700; color: #e8e8f0; margin-bottom: 0.5rem;" />
<div style="width: 80px; height: 2px; background: linear-gradient(90deg, #00f0ff, #b400ff, transparent); margin: 1rem 0;"></div>

<div style="display: grid; grid-template-columns: 1fr 1px 1fr; gap: 2.5rem; flex: 1; overflow: hidden;">
<div style="position: relative; overflow-y: auto;">
<div style="position: absolute; top: -8px; left: 0; right: 0; height: 2px; background: linear-gradient(90deg, #00f0ff, transparent);"></div>
<div style="padding-top: 1.2rem;">
<div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.6rem;">
<span class="tag tag-cyan">Workflow</span>
</div>
<h2 style="font-family: var(--slidev-font-sans); font-size: 1rem; font-weight: 600; color: rgba(0,240,255,0.9); margin-bottom: 0.5rem;">Topics to be covered in order:</h2>
<ul class="styled-list">
<li>Prerequisite: Understanding of basic CSA and virtual memory concepts</li>
<li>Introduction to parallelism</li>
<li>Shortcomings of traditional UMA</li>
<li>Architecture behind NUMA</li>
<li>Memory placement policies</li>
<li>Possible optimizations</li>
<li>Performance impacts</li>
<li>Applications in systems</li>
</ul>
</div>
</div>
<div style="background: linear-gradient(180deg, rgba(0,240,255,0.15), rgba(180,0,255,0.15), transparent); width: 1px;"></div>
<div style="position: relative; overflow-y: auto;">
<div style="position: absolute; top: -8px; left: 0; right: 0; height: 2px; background: linear-gradient(90deg, #b400ff, transparent);"></div>
<div style="padding-top: 1.2rem;">
<div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.6rem;">
<span class="tag tag-purple">References</span>
</div>
<h2 style="font-family: var(--slidev-font-sans); font-size: 1rem; font-weight: 600; color: rgba(180,0,255,0.9); margin-bottom: 0.8rem;">Sources</h2>
<div style="color: var(--c-text-dim); font-size: 0.7rem; line-height: 1.8;">
<div style="margin-bottom: 0.6rem; padding-left: 1rem; border-left: 2px solid rgba(180,0,255,0.2);">Thomas, Gael. "Non uniform memory access", Universite Paris-Saclay.</div>
<div style="margin-bottom: 0.6rem; padding-left: 1rem; border-left: 2px solid rgba(0,240,255,0.2);">Lamater, Christopher. "NUMA (Non-Uniform Memory Access): An Overview", ResearchGate.</div>
<div style="margin-bottom: 0.6rem; padding-left: 1rem; border-left: 2px solid rgba(255,0,60,0.2);">Unknown Author(s). "numa(7) - Linux manual page", Linux/UNIX system programming training.</div>
<div style="margin-bottom: 0.6rem; padding-left: 1rem; border-left: 2px solid rgba(180,0,255,0.2);">van Riel, Rik. "Automatic NUMA Balancing", Red Hat.</div>
</div>
</div>
</div>
</div>
</div>
<StatusBar />
</div>

---
transition: slide-down
---

<div style="position: absolute; top: 0; left: 0; right: 0; bottom: 0; overflow: hidden; background: #050508; z-index: 10;">
<NodeGraph />
<div style="position: absolute; top: 0; left: 0; right: 0; bottom: 0; background: radial-gradient(ellipse at 50% 50%, rgba(255,0,60,0.04) 0%, rgba(255,0,60,0) 50%), radial-gradient(ellipse at 30% 30%, rgba(0,240,255,0.04) 0%, rgba(0,240,255,0) 50%); pointer-events: none;"></div>
<GridOverlay />
<div style="position: relative; z-index: 20; display: flex; flex-direction: column; justify-content: center; align-items: center; height: 100%; text-align: center; padding: 3rem 5rem;">
<GlitchText text="Summary" tag="h1" style="font-size: 2.8rem; font-weight: 700; color: #e8e8f0;" />
<div style="width: 120px; height: 2px; background: linear-gradient(90deg, transparent, #00f0ff, #ff003c, transparent); margin: 1.5rem auto;"></div>

<div style="text-align: left; max-width: 700px; margin-top: 1.5rem;">
<div style="color: var(--c-text-dim); font-size: 0.85rem; margin-bottom: 1.2rem;">In essence,</div>

<div style="margin-bottom: 1.5rem;">
<div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.8rem;">
<span class="tag tag-cyan">Why NUMA?</span>
</div>
<div style="color: var(--c-text-dim); font-size: 0.8rem; margin-bottom: 0.5rem;">NUMA is worth researching about by virtue of being:</div>
<ul class="styled-list">
<li>An interesting application of multiprocessing</li>
<li>Utilized in modern operating systems</li>
<li>Openly accessible and documented</li>
<li>A relatively easy-to-understand implementation</li>
</ul>
</div>

<div>
<div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.8rem;">
<span class="tag tag-red">Coverage</span>
</div>
<div style="color: var(--c-text-dim); font-size: 0.8rem; margin-bottom: 0.5rem;">Following topics are to be covered:</div>
<ul class="styled-list">
<li>Architecture Overview and System Model</li>
<li>Hardware Organisation and Interconnection</li>
<li>Memory Hierarchy and Performance</li>
<li>OS Support, Scheduling and Applications</li>
</ul>
</div>
</div>
</div>
<StatusBar />
</div>
