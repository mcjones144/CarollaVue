<template>
  <footer class="bg-charcoal-light border-t border-white/10 py-12">
    <div class="max-w-7xl mx-auto px-6 lg:px-12 flex flex-col md:flex-row items-center justify-between gap-6">
      <div>
        <p class="font-serif text-lg text-white">Carolla Asset Management</p>
        <p class="text-xs text-white/40 mt-1 uppercase tracking-widest">Unlocking value in partnership</p>
      </div>

      <nav class="flex gap-8">
        <NuxtLink
          v-for="link in links"
          :key="link.href"
          :to="link.href"
          class="text-xs uppercase tracking-widest text-white/50 hover:text-gold transition-colors"
        >
          {{ link.label }}
        </NuxtLink>
      </nav>

      <p class="text-xs text-white/30">© {{ new Date().getFullYear() }} Carolla Asset Management</p>
    </div>
  </footer>
</template>

<script setup lang="ts">
const links = [
  { href: '/uk', label: 'UK' },
  { href: '/spain', label: 'Spain' },
  { href: '/people', label: 'People' },
  { href: '/about', label: 'About' },
]
</script>
