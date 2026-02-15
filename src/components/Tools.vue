<template>
  <section id="skills" class="relative overflow-hidden bg-slate-950 py-16 text-white sm:py-20">
    <div class="pointer-events-none absolute inset-0">
      <div
        class="absolute -top-28 -left-28 h-72 w-72 rounded-full bg-fuchsia-500/12 blur-3xl"
      ></div>
      <div
        class="absolute -bottom-28 -right-28 h-72 w-72 rounded-full bg-cyan-400/12 blur-3xl"
      ></div>
      <div
        class="absolute inset-0 bg-[radial-gradient(circle_at_top,rgba(255,255,255,0.06),transparent_60%)]"
      ></div>
    </div>

    <div class="relative mx-auto w-full max-w-7xl 2xl:max-w-352 px-4 sm:px-6 lg:px-10">
      <div class="grid items-center gap-10 lg:grid-cols-[3fr_2fr]">
        <div class="relative z-10">
          <p
            class="inline-flex items-center gap-2 rounded-full bg-white/10 px-4 py-2 text-xs text-white/75 ring-1 ring-white/15"
          >
            <span class="h-2 w-2 rounded-full bg-emerald-400"></span>
            Toolbox
          </p>

          <h2 class="mt-4 text-3xl font-black tracking-tight sm:text-4xl">
            Tools I use to deliver
            <span
              class="text-transparent bg-clip-text bg-gradient-to-r from-cyan-300 to-fuchsia-300"
            >
              results
            </span>
          </h2>

          <p class="mt-3 max-w-2xl leading-relaxed text-white/70">
            A focused toolkit for design, planning, reporting, and publishing.
          </p>

          <div class="mt-6 flex flex-wrap gap-2">
            <span
              class="inline-flex items-center rounded-full bg-white/5 px-3 py-1.5 text-xs text-white/75 ring-1 ring-white/10"
              >Design</span
            >
            <span
              class="inline-flex items-center rounded-full bg-white/5 px-3 py-1.5 text-xs text-white/75 ring-1 ring-white/10"
              >Workflow</span
            >
            <span
              class="inline-flex items-center rounded-full bg-white/5 px-3 py-1.5 text-xs text-white/75 ring-1 ring-white/10"
              >Reporting</span
            >
            <span
              class="inline-flex items-center rounded-full bg-white/5 px-3 py-1.5 text-xs text-white/75 ring-1 ring-white/10"
              >Publishing</span
            >
          </div>
        </div>

        <div class="relative z-0 h-[260px] sm:h-[320px] lg:col-start-2 lg:h-[360px]">
          <div
            v-for="(tool, i) in tools"
            :key="tool.name"
            class="float absolute select-none"
            :class="animClass(i)"
            :style="styleFor(i)"
          >
            <div class="tooltip">{{ tool.name }}</div>

            <div class="lift">
              <div class="lift-halo"></div>
              <img
                :src="tool.src"
                :alt="tool.name"
                class="h-10 w-10 object-contain opacity-95 sm:h-12 sm:w-12"
                loading="lazy"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import adobe from '../assets/tools/adobe.png';
import affinity from '../assets/tools/affinity.png';
import figma from '../assets/tools/figma.png';
import framer from '../assets/tools/framer.png';
import microsoft from '../assets/tools/microsoft.png';
import miro from '../assets/tools/miro.png';
import notion from '../assets/tools/notion.png';
import powerbi from '../assets/tools/powerbi.png';
import wordpress from '../assets/tools/wordpress.png';

const tools = [
  { name: 'Adobe', src: adobe },
  { name: 'Affinity', src: affinity },
  { name: 'Figma', src: figma },
  { name: 'Framer', src: framer },
  { name: 'Microsoft', src: microsoft },
  { name: 'Miro', src: miro },
  { name: 'Notion', src: notion },
  { name: 'Power BI', src: powerbi },
  { name: 'WordPress', src: wordpress },
];

const positions = [
  { x: 12, y: 18, s: 1.05 },
  { x: 48, y: 12, s: 0.95 },
  { x: 86, y: 20, s: 1.0 },
  { x: 22, y: 46, s: 0.92 },
  { x: 62, y: 40, s: 1.06 },
  { x: 90, y: 52, s: 0.9 },
  { x: 10, y: 72, s: 0.98 },
  { x: 46, y: 78, s: 0.92 },
  { x: 80, y: 86, s: 0.98 },
];

const durations = ['4.3s', '5.1s', '6.4s', '7.2s', '5.7s', '4.9s', '6.9s', '5.4s', '7.8s'];
const delays = ['-0.3s', '-1.7s', '-2.9s', '-0.9s', '-3.6s', '-2.2s', '-4.1s', '-1.1s', '-3.0s'];
const anims = ['float-1', 'float-2', 'float-3', 'float-4', 'float-5'];

function styleFor(i) {
  const p = positions[i % positions.length];
  return {
    left: p.x + '%',
    top: p.y + '%',
    '--scale': p.s,
    animationDuration: durations[i % durations.length],
    animationDelay: delays[i % delays.length],
  };
}

function animClass(i) {
  return anims[i % anims.length];
}
</script>

<style scoped>
.float {
  animation-timing-function: ease-in-out;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}

.float-1 {
  animation-name: float-1;
}
.float-2 {
  animation-name: float-2;
}
.float-3 {
  animation-name: float-3;
}
.float-4 {
  animation-name: float-4;
}
.float-5 {
  animation-name: float-5;
}

.lift {
  position: relative;
  display: grid;
  place-items: center;
  filter: drop-shadow(0 8px 10px rgba(0, 0, 0, 0.28)) drop-shadow(0 26px 28px rgba(0, 0, 0, 0.4));
}

.lift-halo {
  position: absolute;
  inset: -10px;
  border-radius: 999px;
  background: radial-gradient(circle, rgba(255, 255, 255, 0.05), transparent 70%);
  opacity: 0.5;
  filter: blur(1px);
  pointer-events: none;
}

.tooltip {
  position: absolute;
  left: 50%;
  bottom: calc(100% + 10px);
  transform: translateX(-50%);
  white-space: nowrap;
  padding: 6px 10px;
  border-radius: 999px;
  background: rgba(2, 6, 23, 0.75);
  color: rgba(255, 255, 255, 0.9);
  font-size: 12px;
  line-height: 1;
  opacity: 0;
  pointer-events: none;
  transition:
    opacity 180ms ease,
    transform 180ms ease;
  backdrop-filter: blur(8px);
}

.tooltip::after {
  content: '';
  position: absolute;
  left: 50%;
  top: 100%;
  transform: translateX(-50%);
  border: 6px solid transparent;
  border-top-color: rgba(2, 6, 23, 0.75);
}

.float:hover .tooltip {
  opacity: 1;
  transform: translateX(-50%) translateY(-2px);
}

@media (prefers-reduced-motion: reduce) {
  .float {
    animation: none !important;
  }
}

@keyframes float-1 {
  0% {
    transform: translate(-50%, -50%) scale(var(--scale));
  }
  100% {
    transform: translate(calc(-50% + 10px), calc(-50% - 12px)) scale(var(--scale));
  }
}
@keyframes float-2 {
  0% {
    transform: translate(-50%, -50%) scale(var(--scale));
  }
  100% {
    transform: translate(calc(-50% - 12px), calc(-50% + 10px)) scale(var(--scale));
  }
}
@keyframes float-3 {
  0% {
    transform: translate(-50%, -50%) scale(var(--scale));
  }
  100% {
    transform: translate(calc(-50% + 8px), calc(-50% + 14px)) scale(var(--scale));
  }
}
@keyframes float-4 {
  0% {
    transform: translate(-50%, -50%) scale(var(--scale));
  }
  100% {
    transform: translate(calc(-50% - 6px), calc(-50% - 14px)) scale(var(--scale));
  }
}
@keyframes float-5 {
  0% {
    transform: translate(-50%, -50%) scale(var(--scale));
  }
  100% {
    transform: translate(calc(-50% + 14px), calc(-50% + 6px)) scale(var(--scale));
  }
}
</style>
