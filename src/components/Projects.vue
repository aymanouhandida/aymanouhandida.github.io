<script setup>
import OmarShopCase from './case-studies/OmarShopCaseStudy.vue';
import VoltRideCase from './case-studies/VoltRideCase.vue';
import MelangeCase from './case-studies/MelangeCase.vue';
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

      <div class="mt-10 grid gap-6 md:grid-cols-2 lg:grid-cols-3">
        <VoltRideCase />
        <OmarShopCase />
        <MelangeCase />
      </div>
    </div>
  </section>
</template>
