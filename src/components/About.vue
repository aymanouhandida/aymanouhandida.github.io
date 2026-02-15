<template>
  <section id="about" class="relative overflow-hidden bg-slate-950 py-16 text-white sm:py-20">
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

    <div class="relative mx-auto max-w-6xl px-4 sm:px-6 lg:px-8">
      <div class="grid gap-10 lg:grid-cols-[3fr_2fr] lg:items-start">
        <div class="relative z-10">
          <p
            class="inline-flex items-center gap-2 rounded-full bg-white/10 px-4 py-2 text-xs text-white/75 ring-1 ring-white/15"
          >
            <span class="h-2 w-2 rounded-full bg-emerald-400"></span>
            About
          </p>

          <h2 class="mt-4 text-3xl font-black tracking-tight sm:text-4xl">
            I’m a digital marketing student focused on
            <span
              class="text-transparent bg-clip-text bg-gradient-to-r from-cyan-300 to-fuchsia-300"
            >
              measurable growth
            </span>
          </h2>

          <p class="mt-4 max-w-2xl leading-relaxed text-white/70">
            I help small brands and personal projects improve visibility and conversions through
            SEO, smart paid ads, and clear analytics.
          </p>

          <div class="mt-8 flex flex-wrap gap-3">
            <a
              href="#projects"
              class="inline-flex items-center justify-center rounded-full bg-white px-5 py-3 text-sm font-semibold text-slate-950 hover:bg-white/90 transition"
            >
              See Projects
            </a>
          </div>
        </div>

        <div class="relative z-0">
          <div class="card p-6">
            <h3 class="text-lg font-bold tracking-tight">What I can help with</h3>

            <ul class="mt-4 space-y-3 text-sm text-white/70">
              <li class="flex items-start gap-3">
                <span class="check">✓</span>
                <div>
                  <p class="font-semibold text-white/90">SEO & Content</p>
                  <p class="mt-0.5">
                    Keyword research, on-page basics, content plans, and optimization.
                  </p>
                </div>
              </li>

              <li class="flex items-start gap-3">
                <span class="check">✓</span>
                <div>
                  <p class="font-semibold text-white/90">Paid Campaigns</p>
                  <p class="mt-0.5">
                    Meta/Google setup, creatives testing, and weekly optimization.
                  </p>
                </div>
              </li>

              <li class="flex items-start gap-3">
                <span class="check">✓</span>
                <div>
                  <p class="font-semibold text-white/90">Analytics & Reporting</p>
                  <p class="mt-0.5">Dashboards and clean insights.</p>
                </div>
              </li>
            </ul>
          </div>

          <div
            class="pointer-events-none absolute -inset-3 -z-10 rounded-3xl bg-gradient-to-r from-cyan-400/10 to-fuchsia-400/10 blur-2xl"
          ></div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.card {
  border-radius: 1.5rem;
  background: rgba(255, 255, 255, 0.05);
  box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.1);
}

.check {
  margin-top: 0.125rem;
  display: grid;
  place-items: center;
  height: 1.5rem;
  width: 1.5rem;
  border-radius: 9999px;
  background: rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.1);
  color: rgba(255, 255, 255, 0.9);
  flex: 0 0 auto;
}
</style>
