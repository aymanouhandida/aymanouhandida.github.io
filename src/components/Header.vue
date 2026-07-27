<template>
  <header class="relative min-h-screen overflow-hidden bg-slate-950 text-white select-none">
    <div class="pointer-events-none absolute inset-0">
      <div
        class="absolute -top-32 -left-32 h-80 w-80 rounded-full bg-fuchsia-500/20 blur-3xl"
      ></div>
      <div
        class="absolute -bottom-32 -right-32 h-80 w-80 rounded-full bg-cyan-400/20 blur-3xl"
      ></div>
      <div
        class="absolute inset-0 bg-[radial-linear(circle_at_top,rgba(255,255,255,0.10),transparent_55%)]"
      ></div>
    </div>

    <div class="relative mx-auto w-full max-w-7xl 2xl:max-w-352 px-4 sm:px-6 lg:px-10">
      <nav class="flex items-center justify-between py-6">
        <a href="/" class="inline-flex items-center gap-2">
          <div class="leading-tight">
            <div class="text-sm font-semibold tracking-widest">AYMAN OUHANDIDA</div>
          </div>
        </a>

        <div class="hidden items-center gap-1 md:flex">
          <a
            v-for="item in nav"
            :key="item.href"
            :href="item.href"
            class="rounded-full px-4 py-2 text-sm text-white/80 hover:text-white hover:bg-white/10 ring-1 ring-transparent hover:ring-white/10 transition"
          >
            {{ item.label }}
          </a>
        </div>

        <div class="flex items-center gap-2">
          <button
            type="button"
            class="inline-flex items-center justify-center rounded-xl bg-white/10 p-2 ring-1 ring-white/15 hover:bg-white/15 transition"
            :aria-label="isDark ? 'Switch to light mode' : 'Switch to dark mode'"
            :title="isDark ? 'Switch to light mode' : 'Switch to dark mode'"
            @click="toggleTheme"
          >
            <svg
              v-if="isDark"
              viewBox="0 0 24 24"
              class="h-5 w-5"
              fill="none"
              stroke="currentColor"
              stroke-width="1.8"
              aria-hidden="true"
            >
              <circle cx="12" cy="12" r="3.5" />
              <path d="M12 2v2M12 20v2M4.93 4.93l1.42 1.42M17.66 17.66l1.41 1.41M2 12h2M20 12h2M4.93 19.07l1.42-1.42M17.66 6.34l1.41-1.41" />
            </svg>
            <svg
              v-else
              viewBox="0 0 24 24"
              class="h-5 w-5"
              fill="none"
              stroke="currentColor"
              stroke-width="1.8"
              aria-hidden="true"
            >
              <path d="M20.5 14.5A8.5 8.5 0 0 1 9.5 3.5a8.5 8.5 0 1 0 11 11Z" />
            </svg>
          </button>

          <a
            :href="instagramUrl"
            target="_blank"
            rel="noopener noreferrer"
            aria-label="Instagram"
            class="hidden sm:inline-flex items-center justify-center rounded-xl bg-white/10 p-2 ring-1 ring-white/15 hover:bg-white/15 transition"
          >
            <svg
              viewBox="0 0 24 24"
              class="h-5 w-5"
              fill="none"
              stroke="currentColor"
              stroke-width="1.8"
              aria-hidden="true"
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
            class="hidden sm:inline-flex items-center justify-center rounded-xl bg-white/10 p-2 ring-1 ring-white/15 hover:bg-white/15 transition"
          >
            <svg viewBox="0 0 24 24" class="h-5 w-5" fill="currentColor" aria-hidden="true">
              <path
                d="M6.94 6.5A2.06 2.06 0 1 1 6.94 2.38a2.06 2.06 0 0 1 0 4.12ZM5 21.62h3.9V8.12H5v13.5ZM13.02 8.12H9.3v13.5h3.72v-7.1c0-1.97.37-3.88 2.8-3.88 2.4 0 2.43 2.25 2.43 4v6.98H22v-7.78c0-3.82-.82-6.75-5.27-6.75-2.14 0-3.58 1.17-4.17 2.27h-.04V8.12Z"
              />
            </svg>
          </a>

          <a
            :href="githubUrl"
            target="_blank"
            rel="noopener noreferrer"
            aria-label="GitHub"
            class="hidden sm:inline-flex items-center justify-center rounded-xl bg-white/10 p-2 ring-1 ring-white/15 hover:bg-white/15 transition"
          >
            <svg viewBox="0 0 24 24" class="h-5 w-5" fill="currentColor" aria-hidden="true">
              <path
                fill-rule="evenodd"
                clip-rule="evenodd"
                d="M12 .5C5.73.5.75 5.63.75 12c0 5.11 3.29 9.44 7.86 10.97.57.11.78-.25.78-.56v-2.06c-3.2.72-3.88-1.39-3.88-1.39-.53-1.37-1.29-1.73-1.29-1.73-1.06-.74.08-.73.08-.73 1.17.08 1.79 1.23 1.79 1.23 1.04 1.82 2.73 1.29 3.4.99.11-.77.41-1.29.74-1.59-2.55-.3-5.23-1.31-5.23-5.83 0-1.29.45-2.34 1.19-3.17-.12-.3-.52-1.52.11-3.16 0 0 .97-.31 3.18 1.21.92-.26 1.91-.38 2.9-.39.99.01 1.98.13 2.9.39 2.21-1.52 3.18-1.21 3.18-1.21.63 1.64.23 2.86.11 3.16.74.83 1.19 1.88 1.19 3.17 0 4.53-2.69 5.53-5.25 5.82.42.37.79 1.1.79 2.22v3.29c0 .31.21.68.79.56 4.57-1.53 7.86-5.86 7.86-10.97C23.25 5.63 18.27.5 12 .5Z"
              />
            </svg>
          </a>

          <a
            href="#contact"
            class="hidden sm:inline-flex items-center justify-center rounded-full px-4 py-2 text-sm font-semibold bg-white text-slate-950 hover:bg-white/90 transition"
          >
            Contact
          </a>

          <button
            class="md:hidden inline-flex items-center justify-center rounded-xl bg-white/10 p-2 ring-1 ring-white/15 hover:bg-white/15 transition"
            @click="open = !open"
            aria-label="Open menu"
          >
            <svg
              v-if="!open"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.8"
              stroke="currentColor"
              class="h-5 w-5"
              aria-hidden="true"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M3.75 6.75h16.5M3.75 12h16.5M3.75 17.25h16.5"
              />
            </svg>

            <svg
              v-else
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.8"
              stroke="currentColor"
              class="h-5 w-5"
              aria-hidden="true"
            >
              <path stroke-linecap="round" stroke-linejoin="round" d="M6 18 18 6M6 6l12 12" />
            </svg>
          </button>
        </div>
      </nav>

      <div v-if="open" class="md:hidden pb-4">
        <div class="rounded-2xl bg-white/5 ring-1 ring-white/10 p-2">
          <a
            v-for="item in nav"
            :key="item.href"
            :href="item.href"
            class="block rounded-xl px-4 py-3 text-sm text-white/80 hover:text-white hover:bg-white/10 transition"
            @click="open = false"
          >
            {{ item.label }}
          </a>

          <a
            href="#contact"
            class="mt-1 block rounded-xl px-4 py-3 text-sm font-semibold bg-white text-slate-950 hover:bg-white/90 transition text-center"
            @click="open = false"
          >
            Contact
          </a>
        </div>
      </div>

      <section class="grid items-center gap-10 pb-14 pt-8 md:pb-20 md:pt-12 lg:grid-cols-[3fr_2fr]">
        <div>
          <p
            class="inline-flex items-center gap-2 rounded-full bg-white/10 px-4 py-2 text-xs text-white/75 ring-1 ring-white/15"
          >
            <span class="h-2 w-2 rounded-full bg-emerald-400"></span>
            Available for internships & freelance projects
          </p>

          <h1 class="mt-5 text-4xl font-black tracking-tight sm:text-5xl">
            I help brands grow with
            <span class="text-transparent bg-clip-text bg-linear-to-r from-cyan-300 to-fuchsia-300">
              SEO, Ads & Analytics
            </span>
          </h1>

          <p class="mt-4 text-base sm:text-lg text-white/70 leading-relaxed">
            Digital marketing student focused on measurable growth through smarter campaigns and
            clear reporting. Based in Rabat 📍
          </p>

          <div class="mt-6 flex flex-wrap gap-3">
            <a
              href="#projects"
              class="inline-flex items-center justify-center rounded-full px-[1.2rem] py-[0.8rem] text-sm font-semibold bg-white/10 text-white hover:bg-white/15 ring-1 ring-white/15 transition"
            >
              See Projects
            </a>

            <a
              href="#contact"
              class="inline-flex items-center justify-center rounded-full px-5 py-3 text-sm font-semibold bg-white text-slate-950 hover:bg-white/90 transition"
            >
              Contact
            </a>
          </div>

          <div class="mt-6 flex flex-wrap gap-2">
            <span
              class="inline-flex items-center rounded-full bg-white/5 ring-1 ring-white/10 px-3 py-1.5 text-xs text-white/75"
              >SEO</span
            >
            <span
              class="inline-flex items-center rounded-full bg-white/5 ring-1 ring-white/10 px-3 py-1.5 text-xs text-white/75"
              >Meta Ads</span
            >
            <span
              class="inline-flex items-center rounded-full bg-white/5 ring-1 ring-white/10 px-3 py-1.5 text-xs text-white/75"
              >Google Ads</span
            >
            <span
              class="inline-flex items-center rounded-full bg-white/5 ring-1 ring-white/10 px-3 py-1.5 text-xs text-white/75"
              >UX/UI Design</span
            >
            <span
              class="inline-flex items-center rounded-full bg-white/5 ring-1 ring-white/10 px-3 py-1.5 text-xs text-white/75"
              >Content Strategy</span
            >
            <span
              class="inline-flex items-center rounded-full bg-white/5 ring-1 ring-white/10 px-3 py-1.5 text-xs text-white/75"
              >Email Marketing</span
            >
          </div>

          <div class="mt-5 flex items-center gap-4">
            <a
              :href="linkedinUrl"
              target="_blank"
              rel="noopener noreferrer"
              aria-label="LinkedIn"
              class="inline-flex h-10 w-10 items-center justify-center rounded-xl text-white/80 ring-1 ring-white/10 hover:text-white hover:bg-white/5 hover:ring-white/20 transition"
            >
              <svg viewBox="0 0 24 24" class="h-5 w-5" fill="currentColor" aria-hidden="true">
                <path
                  d="M6.94 6.5A2.06 2.06 0 1 1 6.94 2.38a2.06 2.06 0 0 1 0 4.12ZM5 21.62h3.9V8.12H5v13.5ZM13.02 8.12H9.3v13.5h3.72v-7.1c0-1.97.37-3.88 2.8-3.88 2.4 0 2.43 2.25 2.43 4v6.98H22v-7.78c0-3.82-.82-6.75-5.27-6.75-2.14 0-3.58 1.17-4.17 2.27h-.04V8.12Z"
                />
              </svg>
            </a>

            <a
              :href="instagramUrl"
              target="_blank"
              rel="noopener noreferrer"
              aria-label="Instagram"
              class="inline-flex h-10 w-10 items-center justify-center rounded-xl text-white/80 ring-1 ring-white/10 hover:text-white hover:bg-white/5 hover:ring-white/20 transition"
            >
              <svg
                viewBox="0 0 24 24"
                class="h-5 w-5"
                fill="none"
                stroke="currentColor"
                stroke-width="1.8"
                aria-hidden="true"
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
              :href="githubUrl"
              target="_blank"
              rel="noopener noreferrer"
              aria-label="GitHub"
              class="inline-flex h-10 w-10 items-center justify-center rounded-xl text-white/80 ring-1 ring-white/10 hover:text-white hover:bg-white/5 hover:ring-white/20 transition"
            >
              <svg viewBox="0 0 24 24" class="h-5 w-5" fill="currentColor" aria-hidden="true">
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M12 .5C5.73.5.75 5.63.75 12c0 5.11 3.29 9.44 7.86 10.97.57.11.78-.25.78-.56v-2.06c-3.2.72-3.88-1.39-3.88-1.39-.53-1.37-1.29-1.73-1.29-1.73-1.06-.74.08-.73.08-.73 1.17.08 1.79 1.23 1.79 1.23 1.04 1.82 2.73 1.29 3.4.99.11-.77.41-1.29.74-1.59-2.55-.3-5.23-1.31-5.23-5.83 0-1.29.45-2.34 1.19-3.17-.12-.3-.52-1.52.11-3.16 0 0 .97-.31 3.18 1.21.92-.26 1.91-.38 2.9-.39.99.01 1.98.13 2.9.39 2.21-1.52 3.18-1.21 3.18-1.21.63 1.64.23 2.86.11 3.16.74.83 1.19 1.88 1.19 3.17 0 4.53-2.69 5.53-5.25 5.82.42.37.79 1.1.79 2.22v3.29c0 .31.21.68.79.56 4.57-1.53 7.86-5.86 7.86-10.97C23.25 5.63 18.27.5 12 .5Z"
                />
              </svg>
            </a>
          </div>
        </div>

        <div class="relative ml-auto">
          <div
            class="absolute -inset-2 rounded-3xl bg-linear-to-r from-cyan-400/20 to-fuchsia-400/20 blur-2xl"
          ></div>

          <div class="relative w-fit rounded-3xl bg-white/5 ring-1 ring-white/10 p-3 sm:p-4">
            <div class="relative w-fit overflow-hidden rounded-2xl ring-1 ring-white/10">
              <img
                :src="profilePhoto"
                alt="Portrait photo"
                class="w-88 object-cover"
                loading="lazy"
              />
              <div
                class="pointer-events-none absolute inset-0 bg-linear-to-t from-slate-950/40 via-transparent to-transparent"
              ></div>
            </div>
          </div>
        </div>
      </section>
    </div>
  </header>
</template>

<script setup>
import profilePhoto from '@/assets/profile.png';
import { ref } from 'vue';

const open = ref(false);
const isDark = ref(document.documentElement.classList.contains('dark'));

function toggleTheme() {
  isDark.value = !isDark.value;
  document.documentElement.classList.toggle('dark', isDark.value);
  localStorage.setItem('theme', isDark.value ? 'dark' : 'light');
}

const nav = [
  { label: 'About', href: '#about' },
  { label: 'Projects', href: '#projects' },
  { label: 'Skills', href: '#skills' },
];

const instagramUrl = 'https://www.instagram.com/aymanouhandida/';
const linkedinUrl = 'https://www.linkedin.com/in/ayman-ouhandida-23994930a/';
const githubUrl = 'https://github.com/aymanouhandida';
</script>
