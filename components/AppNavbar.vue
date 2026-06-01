<template>
  <header
    :class="[
      'fixed top-0 left-0 right-0 z-50 transition-all duration-500',
      scrolled || menuOpen
        ? 'bg-charcoal/95 backdrop-blur-md border-b border-white/10'
        : 'bg-transparent'
    ]"
  >
    <nav class="max-w-7xl mx-auto px-6 lg:px-12 h-20 flex items-center justify-between">
      <!-- Logo -->
      <NuxtLink to="/" class="flex flex-col leading-none group">
        <span class="font-serif text-lg font-semibold text-white tracking-wide group-hover:text-gold transition-colors">
          Carolla
        </span>
        <span class="text-[10px] uppercase tracking-[0.25em] text-gold/80 font-medium">
          Asset Management
        </span>
      </NuxtLink>

      <!-- Desktop links -->
      <ul class="hidden md:flex items-center gap-10">
        <li v-for="link in links" :key="link.href">
          <NuxtLink
            :to="link.href"
            class="text-sm tracking-wide transition-colors relative group"
            :class="$route.path === link.href ? 'text-gold' : 'text-white/70 hover:text-white'"
          >
            {{ link.label }}
            <span
              class="absolute -bottom-1 left-0 h-px bg-gold transition-all duration-300"
              :class="$route.path === link.href ? 'w-full' : 'w-0 group-hover:w-full'"
            />
          </NuxtLink>
        </li>
      </ul>

      <!-- Mobile hamburger -->
      <button
        class="md:hidden flex flex-col gap-1.5 p-2"
        @click="menuOpen = !menuOpen"
        aria-label="Toggle menu"
      >
        <span class="block w-6 h-px bg-white transition-all duration-300" :class="menuOpen ? 'rotate-45 translate-y-2' : ''" />
        <span class="block w-6 h-px bg-white transition-all duration-300" :class="menuOpen ? 'opacity-0' : ''" />
        <span class="block w-6 h-px bg-white transition-all duration-300" :class="menuOpen ? '-rotate-45 -translate-y-2' : ''" />
      </button>
    </nav>

    <!-- Mobile menu -->
    <div class="md:hidden overflow-hidden transition-all duration-300" :class="menuOpen ? 'max-h-64' : 'max-h-0'">
      <ul class="px-6 pb-6 flex flex-col gap-5">
        <li v-for="link in links" :key="link.href">
          <NuxtLink
            :to="link.href"
            @click="menuOpen = false"
            class="text-sm tracking-wide transition-colors"
            :class="$route.path === link.href ? 'text-gold' : 'text-white/70 hover:text-white'"
          >
            {{ link.label }}
          </NuxtLink>
        </li>
      </ul>
    </div>
  </header>
</template>

<script setup lang="ts">
const scrolled = ref(false)
const menuOpen = ref(false)

const links = [
  { href: '/uk', label: 'UK' },
  { href: '/spain', label: 'Spain' },
  { href: '/people', label: 'People' },
  { href: '/about', label: 'About' },
]

onMounted(() => {
  window.addEventListener('scroll', () => {
    scrolled.value = window.scrollY > 40
  })
})
</script>
