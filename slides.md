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
  sans: 'Space Grotesk'
  mono: 'JetBrains Mono'
---

<div class="relative w-full h-full overflow-hidden" style="background: #050508;">
<NodeGraph />
<div class="absolute inset-0" style="background: radial-gradient(ellipse at 50% 40%, rgba(0,240,255,0.06) 0%, transparent 60%);"></div>
<div class="absolute inset-0" style="background: radial-gradient(ellipse at 70% 80%, rgba(255,0,60,0.04) 0%, transparent 50%);"></div>
<GridOverlay />
<div class="relative z-20 flex flex-col justify-center items-start h-full" style="padding: 4rem 5rem;">
<div style="font-family: 'JetBrains Mono', monospace; font-size: 0.6rem; letter-spacing: 0.25em; text-transform: uppercase; color: rgba(0,240,255,0.4); margin-bottom: 2rem;">
CSA Project // Computer System Architecture
</div>
<div style="position: relative;">
<div style="position: absolute; top: -20px; left: -10px; font-family: 'Space Grotesk', sans-serif; font-size: 8rem; font-weight: 700; color: transparent; -webkit-text-stroke: 1px rgba(0,240,255,0.06); line-height: 1; pointer-events: none; user-select: none;">
NUMA
</div>
<GlitchText text="Non-uniform Memory Access" tag="h1" style="font-size: 2.8rem; font-weight: 700; color: #e8e8f0; line-height: 1.1; position: relative; z-index: 1;" />
</div>
<div style="margin-top: 1rem; font-family: 'JetBrains Mono', monospace; font-size: 0.85rem; color: rgba(0,240,255,0.6); letter-spacing: 0.05em;">
Memory design with a twist
</div>
<div style="width: 120px; height: 2px; background: linear-gradient(90deg, #00f0ff, #ff003c, transparent); margin: 2rem 0;"></div>
<div style="color: rgba(232,232,240,0.5); font-size: 0.75rem; letter-spacing: 0.02em; line-height: 2;">
Presented to you by~
</div>
<div style="display: flex; gap: 1.5rem; margin-top: 0.5rem; flex-wrap: wrap;">
<span class="tag tag-cyan">Aryan Nagdawane</span>
<span class="tag tag-red">Suyash Chandel</span>
<span class="tag tag-purple">Praveen Parakh</span>
<span class="tag tag-cyan">Het DharmendraBhai Dhinoja</span>
</div>
<div @click="$slidev.nav.next" style="margin-top: 3rem; cursor: pointer; display: flex; align-items: center; gap: 0.5rem; font-family: 'JetBrains Mono', monospace; font-size: 0.7rem; color: rgba(0,240,255,0.4); letter-spacing: 0.1em; transition: color 0.3s;">
<span style="display: inline-block; width: 16px; height: 1px; background: rgba(0,240,255,0.4);"></span>
Let's see what its all about <carbon:arrow-right style="margin-left: 4px;" />
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

<div class="relative w-full h-full overflow-hidden" style="background: #050508;">
<MatrixRain />
<div class="absolute inset-0" style="background: radial-gradient(ellipse at 30% 50%, rgba(180,0,255,0.05) 0%, transparent 60%);"></div>
<GridOverlay />
<div class="relative z-20 flex flex-col h-full" style="padding: 4rem 5rem;">
<div style="display: flex; align-items: center; gap: 1rem; margin-bottom: 1rem;">
<span style="font-family: 'Space Grotesk', sans-serif; font-size: 4rem; font-weight: 700; color: transparent; -webkit-text-stroke: 1px rgba(0,240,255,0.12); line-height: 1;">01</span>
<div>
<div style="font-family: 'JetBrains Mono', monospace; font-size: 0.55rem; letter-spacing: 0.2em; text-transform: uppercase; color: rgba(0,240,255,0.3);">Section</div>
<div style="width: 40px; height: 1px; background: rgba(0,240,255,0.2); margin-top: 4px;"></div>
</div>
</div>
<GlitchText text="Introduction" tag="h1" style="font-size: 2.4rem; font-weight: 700; color: #e8e8f0; margin-bottom: 0.5rem;" />
<div style="width: 80px; height: 2px; background: linear-gradient(90deg, #b400ff, #00f0ff, transparent); margin: 1.5rem 0;"></div>
</div>
<TransitionSound :page="2" src="/swoosh.mp3" />
<StatusBar />
</div>

---
transition: fade
---

<div class="relative w-full h-full overflow-hidden" style="background: #050508;">
<div class="absolute inset-0" style="background: radial-gradient(ellipse at 20% 30%, rgba(0,240,255,0.04) 0%, transparent 50%), radial-gradient(ellipse at 80% 70%, rgba(255,0,60,0.04) 0%, transparent 50%);"></div>
<GridOverlay />
<div class="relative z-20 flex flex-col h-full" style="padding: 3rem 5rem;">
<div style="display: flex; align-items: center; gap: 1rem; margin-bottom: 0.8rem;">
<span style="font-family: 'Space Grotesk', sans-serif; font-size: 4rem; font-weight: 700; color: transparent; -webkit-text-stroke: 1px rgba(0,240,255,0.12); line-height: 1;">02</span>
<div>
<div style="font-family: 'JetBrains Mono', monospace; font-size: 0.55rem; letter-spacing: 0.2em; text-transform: uppercase; color: rgba(0,240,255,0.3);">Distribution</div>
</div>
</div>
<h1 style="font-family: 'Space Grotesk', sans-serif; font-size: 2rem; font-weight: 700; color: #e8e8f0; letter-spacing: -0.03em; margin-bottom: 0.3rem;">Unit Distribution</h1>
<div style="width: 100%; height: 1px; background: linear-gradient(90deg, rgba(0,240,255,0.2), rgba(255,0,60,0.2), transparent); margin-bottom: 2rem;"></div>
<div style="display: grid; grid-template-columns: 1fr 1px 1fr; gap: 2.5rem; flex: 1;">
<div style="position: relative;">
<div style="position: absolute; top: -8px; left: 0; right: 0; height: 2px; background: linear-gradient(90deg, #00f0ff, transparent);"></div>
<div style="padding-top: 1.5rem;">
<div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.8rem;">
<span class="tag tag-cyan">Unit 1</span>
</div>
<h2 style="font-family: 'Space Grotesk', sans-serif; font-size: 1.1rem; font-weight: 600; color: rgba(0,240,255,0.9); margin-bottom: 0.3rem;">Architecture Overview and System Model</h2>
<div style="font-family: 'JetBrains Mono', monospace; font-size: 0.65rem; color: rgba(0,240,255,0.35); letter-spacing: 0.05em; margin-bottom: 1.2rem; font-style: italic;">Covered by Aryan Nagdawade</div>
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
<h2 style="font-family: 'Space Grotesk', sans-serif; font-size: 1.1rem; font-weight: 600; color: rgba(255,0,60,0.9); margin-bottom: 0.3rem;">Hardware Organisation and Interconnection</h2>
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

<div class="relative w-full h-full overflow-hidden" style="background: #050508;">
<div class="absolute inset-0" style="background: radial-gradient(ellipse at 80% 30%, rgba(180,0,255,0.04) 0%, transparent 50%), radial-gradient(ellipse at 20% 70%, rgba(0,240,255,0.04) 0%, transparent 50%);"></div>
<GridOverlay />
<div class="relative z-20 flex flex-col h-full" style="padding: 3rem 5rem;">
<div style="display: flex; align-items: center; gap: 1rem; margin-bottom: 0.8rem;">
<span style="font-family: 'Space Grotesk', sans-serif; font-size: 4rem; font-weight: 700; color: transparent; -webkit-text-stroke: 1px rgba(180,0,255,0.12); line-height: 1;">03</span>
<div>
<div style="font-family: 'JetBrains Mono', monospace; font-size: 0.55rem; letter-spacing: 0.2em; text-transform: uppercase; color: rgba(180,0,255,0.3);">Distribution</div>
</div>
</div>
<h1 style="font-family: 'Space Grotesk', sans-serif; font-size: 2rem; font-weight: 700; color: #e8e8f0; letter-spacing: -0.03em; margin-bottom: 0.3rem;">Unit Distribution</h1>
<div style="width: 100%; height: 1px; background: linear-gradient(90deg, rgba(180,0,255,0.2), rgba(0,240,255,0.2), transparent); margin-bottom: 2rem;"></div>
<div style="display: grid; grid-template-columns: 1fr 1px 1fr; gap: 2.5rem; flex: 1;">
<div style="position: relative;">
<div style="position: absolute; top: -8px; left: 0; right: 0; height: 2px; background: linear-gradient(90deg, #b400ff, transparent);"></div>
<div style="padding-top: 1.5rem;">
<div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.8rem;">
<span class="tag tag-purple">Unit 3</span>
</div>
<h2 style="font-family: 'Space Grotesk', sans-serif; font-size: 1.1rem; font-weight: 600; color: rgba(180,0,255,0.9); margin-bottom: 0.3rem;">Memory Hierarchy and Performance</h2>
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
<h2 style="font-family: 'Space Grotesk', sans-serif; font-size: 1.1rem; font-weight: 600; color: rgba(0,240,255,0.9); margin-bottom: 0.3rem;">OS Support, Scheduling and Applications</h2>
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

<div class="relative w-full h-full overflow-hidden" style="background: #050508;">
<OrbitVis />
<div class="absolute inset-0" style="background: radial-gradient(ellipse at 50% 50%, rgba(0,240,255,0.05) 0%, transparent 60%);"></div>
<GridOverlay />
<div class="relative z-20 flex flex-col justify-center h-full" style="padding: 4rem 5rem;">
<div style="display: flex; align-items: center; gap: 1rem; margin-bottom: 1rem;">
<span style="font-family: 'Space Grotesk', sans-serif; font-size: 4rem; font-weight: 700; color: transparent; -webkit-text-stroke: 1px rgba(0,240,255,0.12); line-height: 1;">04</span>
<div>
<div style="font-family: 'JetBrains Mono', monospace; font-size: 0.55rem; letter-spacing: 0.2em; text-transform: uppercase; color: rgba(0,240,255,0.3);">Process</div>
</div>
</div>
<GlitchText text="Workflow and Resources" tag="h1" style="font-size: 2.4rem; font-weight: 700; color: #e8e8f0;" />
<div style="width: 80px; height: 2px; background: linear-gradient(90deg, #00f0ff, #b400ff, transparent); margin: 1.5rem 0;"></div>
</div>
<StatusBar />
</div>

---
transition: slide-down
---

<div class="relative w-full h-full overflow-hidden" style="background: #050508;">
<NodeGraph />
<div class="absolute inset-0" style="background: radial-gradient(ellipse at 50% 50%, rgba(255,0,60,0.04) 0%, transparent 50%), radial-gradient(ellipse at 30% 30%, rgba(0,240,255,0.04) 0%, transparent 50%);"></div>
<GridOverlay />
<div class="relative z-20 flex flex-col justify-center items-center h-full text-center" style="padding: 4rem 5rem;">
<div style="font-family: 'Space Grotesk', sans-serif; font-size: 8rem; font-weight: 700; color: transparent; -webkit-text-stroke: 1px rgba(0,240,255,0.08); line-height: 1; margin-bottom: 1rem; user-select: none;">
//
</div>
<GlitchText text="Summary" tag="h1" style="font-size: 2.8rem; font-weight: 700; color: #e8e8f0;" />
<div style="width: 120px; height: 2px; background: linear-gradient(90deg, transparent, #00f0ff, #ff003c, transparent); margin: 1.5rem auto;"></div>
</div>
<StatusBar />
</div>
