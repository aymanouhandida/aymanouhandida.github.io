<template>
  <section id="contact" class="relative overflow-hidden bg-slate-950 py-16 text-white sm:py-20">
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
      <p
        class="inline-flex items-center gap-2 rounded-full bg-white/10 px-4 py-2 text-xs text-white/75 ring-1 ring-white/15"
      >
        <span class="h-2 w-2 rounded-full bg-emerald-400"></span>
        Contact
      </p>

      <div class="mt-4 flex flex-col gap-10 lg:flex-row lg:items-center lg:justify-between">
        <h2 class="text-3xl font-black tracking-tight sm:text-4xl">What can I do for you?</h2>

        <div class="grid gap-5 sm:grid-cols-2">
          <div class="flex items-center gap-4 rounded-3xl bg-white/5 p-4 ring-1 ring-white/10">
            <div
              class="grid h-12 w-12 place-items-center rounded-2xl bg-white/10 ring-1 ring-white/10"
            >
              <svg
                viewBox="0 0 24 24"
                class="h-6 w-6 text-cyan-300"
                fill="none"
                stroke="currentColor"
                stroke-width="1.8"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M12 21s7-5.25 7-11a7 7 0 1 0-14 0c0 5.75 7 11 7 11Z"
                />
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M12 10.5a2 2 0 1 0 0-4 2 2 0 0 0 0 4Z"
                />
              </svg>
            </div>

            <div>
              <div class="text-sm font-extrabold">Location</div>
              <div class="mt-1 text-sm text-white/70">Rabat, Morocco</div>
            </div>
          </div>

          <div class="flex items-center gap-4 rounded-3xl bg-white/5 p-4 ring-1 ring-white/10">
            <div
              class="grid h-12 w-12 place-items-center rounded-2xl bg-white/10 ring-1 ring-white/10"
            >
              <svg
                viewBox="0 0 24 24"
                class="h-6 w-6 text-fuchsia-300"
                fill="none"
                stroke="currentColor"
                stroke-width="1.8"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M4 7.5A2.5 2.5 0 0 1 6.5 5h11A2.5 2.5 0 0 1 20 7.5v9A2.5 2.5 0 0 1 17.5 19h-11A2.5 2.5 0 0 1 4 16.5v-9Z"
                />
                <path stroke-linecap="round" stroke-linejoin="round" d="m5.5 7 6.5 5 6.5-5" />
              </svg>
            </div>

            <div>
              <div class="text-sm font-extrabold">Email</div>
              <a
                :href="`mailto:${email}`"
                class="mt-1 inline-flex items-center gap-2 text-sm text-white/70 transition hover:text-white"
              >
                {{ email }}
                <span class="text-white/40">↗</span>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const email = 'aymanoualaeou@gmail.com';
</script>
