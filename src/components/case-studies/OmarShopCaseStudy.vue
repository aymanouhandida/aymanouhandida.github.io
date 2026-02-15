<template>
  <article class="card select-none p-6 sm:p-7">
    <div class="flex items-start justify-between gap-4">
      <div>
        <div class="flex flex-wrap items-center gap-2">
          <span class="badge2">E-commerce UI/UX</span>
          <span class="badge2">Branding</span>
        </div>

        <h3 class="mt-3 text-xl font-bold tracking-tight">Omar Shop. Arabic Perfumes</h3>

        <p class="mt-2 text-sm text-white/70 leading-relaxed">
          E-commerce concept for Arabic perfumes: premium hero, filtered listings, and clean
          checkout.
        </p>
      </div>
    </div>

    <div class="mt-6 flex flex-wrap gap-2">
      <span class="chip">Figma</span>
      <span class="chip">Photoshop</span>
      <span class="chip">UI Design</span>
      <span class="chip">E-commerce</span>
    </div>

    <div class="mt-7 flex flex-wrap items-center gap-3">
      <a
        class="btn btnPrimary"
        href="https://omarshop-3kmk203wc-ayman-ouhandida-s-projects.vercel.app/"
        target="_blank"
        rel="noopener noreferrer"
      >
        Website
      </a>
    </div>
  </article>
</template>

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
  padding: 0.65rem 1.05rem;
  font-size: 0.85rem;
  font-weight: 800;
  line-height: 1;
  text-decoration: none;
  transition:
    background 0.2s ease,
    opacity 0.2s ease,
    transform 0.15s ease;
}

@media (min-width: 640px) {
  .btn {
    padding: 0.78rem 1.15rem;
    font-size: 0.88rem;
  }
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
</style>
