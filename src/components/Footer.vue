<template>
  <footer class="relative overflow-hidden bg-slate-950 text-white">
    <div class="pointer-events-none absolute inset-0">
      <div
        class="absolute -top-24 -left-24 h-64 w-64 rounded-full bg-fuchsia-500/10 blur-3xl"
      ></div>
      <div
        class="absolute -bottom-24 -right-24 h-64 w-64 rounded-full bg-cyan-400/10 blur-3xl"
      ></div>
    </div>

    <div class="relative mx-auto max-w-6xl px-4 sm:px-6 lg:px-8">
      <div class="h-px w-full bg-white/10"></div>

      <div class="flex flex-col gap-6 py-10 sm:flex-row sm:items-center sm:justify-between">
        <div>
          <div class="text-sm font-semibold tracking-widest">AYMAN OUHANDIDA</div>
          <p class="mt-2 text-sm text-white/60">
            Digital marketing • SEO • Ads • Reporting — Rabat, Morocco
          </p>
        </div>

        <div class="flex flex-wrap items-center gap-3">
          <a href="#about" class="text-sm text-white/70 transition hover:text-white">About</a>
          <span class="text-white/20">•</span>

          <a href="#projects" class="text-sm text-white/70 transition hover:text-white">Projects</a>
          <span class="text-white/20">•</span>

          <a href="#skills" class="text-sm text-white/70 transition hover:text-white">Skills</a>
          <span class="text-white/20">•</span>

          <a href="#contact" class="text-sm text-white/70 transition hover:text-white">Contact</a>
        </div>
      </div>

      <div class="flex flex-col gap-4 pb-10 sm:flex-row sm:items-center sm:justify-between">
        <p class="text-sm text-white/50">
          © {{ year }} Ayman Ouhandida · Portfolio developed by
          <a
            href="https://oussamaelkasmi.github.io/"
            target="_blank"
            rel="noopener noreferrer"
            class="transition hover:text-white"
          >
            Oussama El Kasmi <span class="text-white/40">↗</span>
          </a>
        </p>

        <div class="flex items-center gap-3">
          <a
            :href="instagramUrl"
            target="_blank"
            rel="noopener noreferrer"
            aria-label="Instagram"
            class="inline-flex h-10 w-10 items-center justify-center rounded-xl bg-white/5 ring-1 ring-white/10 transition hover:bg-white/10 hover:ring-white/20"
          >
            <svg
              viewBox="0 0 24 24"
              class="h-5 w-5 text-white/80"
              fill="none"
              stroke="currentColor"
              stroke-width="1.8"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M7.5 3.75h9A3.75 3.75 0 0 1 20.25 7.5v9A3.75 3.75 0 0 1 16.5 20.25h-9A3.75 3.75 0 0 1 3.75 16.5v-9A3.75 3.75 0 0 1 7.5 3.75Z"
              />
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M15.75 11.7a3.75 3.75 0 1 1-7.5 0 3.75 3.75 0 0 1 7.5 0Z"
              />
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M17.25 6.75h.008v.008h-.008z"
              />
            </svg>
          </a>

          <a
            :href="linkedinUrl"
            target="_blank"
            rel="noopener noreferrer"
            aria-label="LinkedIn"
            class="inline-flex h-10 w-10 items-center justify-center rounded-xl bg-white/5 ring-1 ring-white/10 transition hover:bg-white/10 hover:ring-white/20"
          >
            <svg viewBox="0 0 24 24" class="h-5 w-5 text-white/80" fill="currentColor">
              <path
                d="M6.94 6.5A2.06 2.06 0 1 1 6.94 2.38a2.06 2.06 0 0 1 0 4.12ZM5 21.62h3.9V8.12H5v13.5ZM13.02 8.12H9.3v13.5h3.72v-7.1c0-1.97.37-3.88 2.8-3.88 2.4 0 2.43 2.25 2.43 4v6.98H22v-7.78c0-3.82-.82-6.75-5.27-6.75-2.14 0-3.58 1.17-4.17 2.27h-.04V8.12Z"
              />
            </svg>
          </a>

          <a
            href="#"
            aria-label="Back to top"
            class="inline-flex h-10 w-10 items-center justify-center rounded-xl bg-white/5 ring-1 ring-white/10 transition hover:bg-white/10 hover:ring-white/20"
          >
            <svg
              viewBox="0 0 24 24"
              class="h-5 w-5 text-white/80"
              fill="none"
              stroke="currentColor"
              stroke-width="1.8"
            >
              <path stroke-linecap="round" stroke-linejoin="round" d="M12 19V5" />
              <path stroke-linecap="round" stroke-linejoin="round" d="m6 11 6-6 6 6" />
            </svg>
          </a>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
const year = new Date().getFullYear();

const instagramUrl = 'https://www.instagram.com/aymanouhandida/';
const linkedinUrl = 'https://www.linkedin.com/in/ayman-ouhandida-23994930a/';
</script>
