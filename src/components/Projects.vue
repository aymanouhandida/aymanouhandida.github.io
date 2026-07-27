<script setup>
import { onMounted, onUnmounted, ref } from 'vue';
import ClassyStyleCase from './case-studies/ClassyStyle.vue';
import MelangeCase from './case-studies/Melange.vue';
import OmarShopCase from './case-studies/OmarShop.vue';
import VoltRideCase from './case-studies/VoltRide.vue';

const projectsTrack = ref(null);
const canScrollPrevious = ref(false);
const canScrollNext = ref(false);

function updateScrollButtons() {
  const track = projectsTrack.value;
  if (!track) return;

  canScrollPrevious.value = track.scrollLeft > 1;
  canScrollNext.value = track.scrollLeft < track.scrollWidth - track.clientWidth - 1;
}

function scrollProjects(direction) {
  projectsTrack.value?.scrollBy({
    left: direction * projectsTrack.value.clientWidth,
    behavior: 'smooth',
  });
}

onMounted(() => {
  updateScrollButtons();
  window.addEventListener('resize', updateScrollButtons);
});

onUnmounted(() => window.removeEventListener('resize', updateScrollButtons));
</script>

<template>
  <section id="projects" class="relative overflow-hidden bg-slate-950 text-white py-16 sm:py-20">
    <div class="pointer-events-none absolute inset-0">
      <div
        class="absolute -top-28 -left-28 h-72 w-72 rounded-full bg-fuchsia-500/10 blur-3xl"
      ></div>
      <div
        class="absolute -bottom-28 -right-28 h-72 w-72 rounded-full bg-cyan-400/10 blur-3xl"
      ></div>
      <div
        class="absolute inset-0 bg-[radial-gradient(circle_at_top,rgba(255,255,255,0.05),transparent_60%)]"
      ></div>
    </div>

    <div class="relative mx-auto w-full max-w-7xl 2xl:max-w-352 px-4 sm:px-6 lg:px-10">
      <div>
        <p
          class="inline-flex items-center gap-2 rounded-full bg-white/10 px-4 py-2 text-xs text-white/75 ring-1 ring-white/15"
        >
          <span class="h-2 w-2 rounded-full bg-emerald-400"></span>
          Projects
        </p>

        <h2 class="mt-4 text-3xl font-black tracking-tight sm:text-4xl">
          Academic projects that simulate
          <span class="text-transparent bg-clip-text bg-gradient-to-r from-cyan-300 to-fuchsia-300"
            >real work</span
          >
        </h2>

        <p class="mt-3 max-w-2xl text-white/70 leading-relaxed">
          Short case studies with deliverables.
        </p>
      </div>

      <div class="relative mt-10">
        <button
          v-show="canScrollPrevious"
          type="button"
          aria-label="Previous projects"
          class="absolute top-0 left-1 z-10 grid h-10 w-10 -translate-y-1/2 place-items-center rounded-full bg-white text-slate-950 shadow-lg ring-1 ring-white/15 transition hover:scale-105 sm:top-1/2 sm:-left-5"
          @click="scrollProjects(-1)"
        >
          <svg viewBox="0 0 24 24" class="h-5 w-5" fill="none" stroke="currentColor" stroke-width="2" aria-hidden="true">
            <path stroke-linecap="round" stroke-linejoin="round" d="m15 18-6-6 6-6" />
          </svg>
        </button>

        <div
          ref="projectsTrack"
          class="projects-track flex gap-6 overflow-x-auto scroll-smooth"
          @scroll.passive="updateScrollButtons"
        >
          <div class="project-slide"><VoltRideCase /></div>
          <div class="project-slide"><OmarShopCase /></div>
          <div class="project-slide"><MelangeCase /></div>
          <div class="project-slide"><ClassyStyleCase /></div>
        </div>

        <button
          v-show="canScrollNext"
          type="button"
          aria-label="Next projects"
          class="absolute top-0 right-1 z-10 grid h-10 w-10 -translate-y-1/2 place-items-center rounded-full bg-white text-slate-950 shadow-lg ring-1 ring-white/15 transition hover:scale-105 sm:top-1/2 sm:-right-5"
          @click="scrollProjects(1)"
        >
          <svg viewBox="0 0 24 24" class="h-5 w-5" fill="none" stroke="currentColor" stroke-width="2" aria-hidden="true">
            <path stroke-linecap="round" stroke-linejoin="round" d="m9 18 6-6-6-6" />
          </svg>
        </button>
      </div>
    </div>
  </section>
</template>

<style scoped>
.projects-track {
  scroll-snap-type: x mandatory;
  scrollbar-width: none;
}

.projects-track::-webkit-scrollbar {
  display: none;
}

.project-slide {
  flex: 0 0 100%;
  scroll-snap-align: start;
}

@media (min-width: 768px) {
  .project-slide {
    flex-basis: calc((100% - 1.5rem) / 2);
  }
}

@media (min-width: 1024px) {
  .project-slide {
    flex-basis: calc((100% - 3rem) / 3);
  }
}
</style>
