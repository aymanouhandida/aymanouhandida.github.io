<template>
  <article class="card select-none p-6 sm:p-7">
    <div class="flex items-start justify-between gap-4">
      <div>
        <div class="flex flex-wrap items-center gap-2">
          <span class="badge2">Branding</span>
          <span class="badge2">Social Content</span>
        </div>

        <h3 class="mt-3 text-xl font-bold tracking-tight">MELANGE</h3>

        <p class="mt-2 text-sm text-white/70 leading-relaxed">
          Visual identity + social creatives concept, built around a clean, premium layout system
          and consistent brand rules.
        </p>
      </div>
    </div>

    <div class="mt-6 flex flex-wrap gap-2">
      <span class="chip">Photoshop</span>
      <span class="chip">Figma</span>
      <span class="chip">Branding</span>
      <span class="chip">Social Media</span>
    </div>

    <div class="mt-7 flex flex-wrap items-center gap-3">
      <button type="button" class="btn btnPrimary cursor-pointer" @click="open = true">
        View Screenshots
      </button>
    </div>

    <Teleport to="body">
      <div
        v-if="open"
        class="overlay"
        role="dialog"
        aria-modal="true"
        @click.self="open = false"
        @keydown.esc="open = false"
        tabindex="-1"
      >
        <div class="panel">
          <div class="masonry">
            <img v-for="(s, i) in shots" :key="i" :src="s" alt="" class="img" loading="lazy" />
          </div>
        </div>
      </div>
    </Teleport>
  </article>
</template>

<script setup>
import { ref } from 'vue';

import m1 from '../../assets/case-studies/melange/1.png';
import m2 from '../../assets/case-studies/melange/2.png';
import m3 from '../../assets/case-studies/melange/3.png';
import m4 from '../../assets/case-studies/melange/4.png';
import m5 from '../../assets/case-studies/melange/5.png';
import m6 from '../../assets/case-studies/melange/6.png';

const open = ref(false);
const shots = [m1, m2, m3, m4, m5, m6];
</script>

<style scoped>
.card {
  border-radius: 1.5rem;
  background: rgba(255, 255, 255, 0.05);
  box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.1);
}

.badge2 {
  font-size: 0.7rem;
  padding: 0.25rem 0.6rem;
  border-radius: 999px;
  background: rgba(34, 211, 238, 0.1);
  box-shadow: inset 0 0 0 1px rgba(34, 211, 238, 0.18);
  color: rgba(165, 243, 252, 0.95);
}

.chip {
  display: inline-flex;
  align-items: center;
  border-radius: 999px;
  padding: 0.35rem 0.7rem;
  font-size: 0.75rem;
  color: rgba(255, 255, 255, 0.75);
  background: rgba(255, 255, 255, 0.05);
  box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.1);
}

.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border-radius: 999px;
  padding: 0.8rem 1.2rem;
  font-size: 0.85rem;
  font-weight: 800;
  line-height: 1;
  text-decoration: none;
  transition:
    background 0.2s ease,
    transform 0.15s ease;
}

.btn:active {
  transform: translateY(1px);
}

.btnPrimary {
  background: white;
  color: rgb(2, 6, 23);
}
.btnPrimary:hover {
  opacity: 0.92;
}

.btnSecondary:hover {
  background: rgba(255, 255, 255, 0.12);
}

.overlay {
  position: fixed;
  inset: 0;
  z-index: 60;
  display: grid;
  place-items: center;
  padding: 1rem;
  background: rgba(2, 6, 23, 0.72);
  backdrop-filter: blur(10px);
}

.panel {
  width: min(980px, 100%);
  max-height: 88vh;
  overflow: auto;
}

.masonry {
  column-count: 2;
  column-gap: 12px;
}

.img {
  width: 100%;
  height: auto;
  display: block;
  margin: 0 0 12px;
  break-inside: avoid;
  -webkit-column-break-inside: avoid;
}

.img {
  width: 100%;
  height: auto;
  display: block;
  object-fit: cover;
}
</style>
