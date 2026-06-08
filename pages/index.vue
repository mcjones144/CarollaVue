<template>
  <div>
    <!-- Hero -->
    <section class="relative h-screen flex items-center justify-center overflow-hidden">
      <div
        class="absolute inset-0 bg-cover bg-center bg-no-repeat"
        style="background-image: url('https://images.squarespace-cdn.com/content/v1/68553a0b1f8c0d662c3653da/1750598845962-0YGIFOJM2OE6GTY3V9CO/unsplash-image-qkfxBc2NQ18.jpg')"
      />
      <div class="absolute inset-0 bg-charcoal/65" />
      <div class="relative z-10 text-center px-6 max-w-4xl mx-auto">
        <p class="section-label mb-6">Established 2022</p>
        <h1 class="font-serif text-6xl sm:text-7xl lg:text-8xl font-semibold text-white leading-[1.05] mb-8">
          Carolla<br />
          <span class="text-gold">Asset</span><br />
          Management
        </h1>
        <p class="text-white/60 text-lg sm:text-xl tracking-wide mb-12">Unlocking value in partnership</p>
        <div class="flex flex-col sm:flex-row gap-4 justify-center">
          <NuxtLink to="/about" class="inline-block px-8 py-3.5 bg-gold text-charcoal text-sm font-semibold uppercase tracking-widest hover:bg-gold-light transition-colors">
            Learn More
          </NuxtLink>
          <NuxtLink to="/uk" class="inline-block px-8 py-3.5 border border-white/30 text-white text-sm font-medium uppercase tracking-widest hover:border-gold hover:text-gold transition-colors">
            Our Projects
          </NuxtLink>
        </div>
      </div>
      <div class="absolute bottom-10 left-1/2 -translate-x-1/2 flex flex-col items-center gap-2 text-white/30">
        <span class="text-xs uppercase tracking-widest">Scroll</span>
        <span class="block w-px h-8 bg-white/20 animate-pulse" />
      </div>
    </section>

    <!-- Intro -->
    <section class="bg-charcoal-light py-24">
      <div class="max-w-7xl mx-auto px-6 lg:px-12 grid md:grid-cols-2 gap-16 items-center">
        <div>
          <p class="section-label mb-4">Who We Are</p>
          <div class="gold-line mb-8" />
          <h2 class="font-serif text-4xl lg:text-5xl font-semibold text-white leading-tight mb-6">
            Experienced professionals.<br />Real results.
          </h2>
          <p class="text-white/60 leading-relaxed mb-8">
            Carolla Asset Management was established in 2022 by a group of experienced property and finance professionals. We work with real estate owners to identify development opportunities and unlock value across portfolios.
          </p>
          <NuxtLink to="/about" class="inline-flex items-center gap-3 text-gold text-sm uppercase tracking-widest group">
            About us
            <span class="block w-8 h-px bg-gold group-hover:w-12 transition-all duration-300" />
          </NuxtLink>
        </div>
        <div class="grid grid-cols-2 gap-6">
          <div v-for="stat in stats" :key="stat.label" class="border border-white/10 p-8 hover:border-gold/40 transition-colors">
            <p class="font-serif text-4xl text-gold font-semibold mb-2">{{ stat.number }}</p>
            <p class="text-white/50 text-sm leading-snug">{{ stat.label }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Markets -->
    <section class="py-24">
      <div class="max-w-7xl mx-auto px-6 lg:px-12">
        <div class="text-center mb-16">
          <p class="section-label mb-4">Our Markets</p>
          <div class="gold-line mx-auto mb-6" />
          <h2 class="font-serif text-4xl font-semibold text-white">Where we operate</h2>
        </div>
        <div class="grid md:grid-cols-2 gap-8">
          <NuxtLink
            v-for="market in markets"
            :key="market.tag"
            :to="market.href"
            class="relative group overflow-hidden block aspect-[4/3]"
          >
            <div
              class="absolute inset-0 bg-cover bg-center transition-transform duration-700 group-hover:scale-105"
              :style="`background-image: url('${market.img}')`"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-charcoal/90 via-charcoal/30 to-transparent" />
            <div class="absolute bottom-0 left-0 p-8">
              <p class="section-label mb-2">{{ market.tag }}</p>
              <h3 class="font-serif text-3xl text-white font-semibold mb-3">{{ market.region }}</h3>
              <p class="text-white/60 text-sm leading-relaxed max-w-xs">{{ market.desc }}</p>
              <span class="inline-flex items-center gap-2 text-gold text-xs uppercase tracking-widest mt-4 group-hover:gap-4 transition-all">
                View projects <span>→</span>
              </span>
            </div>
          </NuxtLink>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
useHead({ title: 'Carolla Asset Management' })

const stats = [
  { number: '3', label: 'Active markets' },
  { number: '2022', label: 'Founded' },
]

const markets = [
  {
    region: 'United Kingdom',
    tag: 'UK',
    href: '/uk',
    desc: 'London and beyond — student accommodation, workforce housing, and joint venture development projects.',
    img: 'https://images.squarespace-cdn.com/content/v1/68553a0b1f8c0d662c3653da/1750599254564-SNAI0WMLL4GDAQYY2DAX/unsplash-image-q140lHKzXZY.jpg',
  },
  {
    region: 'Spain & Gibraltar',
    tag: 'Spain',
    href: '/spain',
    desc: 'Luxury residential development in Sotogrande and the Costa del Sol — townhouses and villas of the highest standard.',
    img: 'https://images.squarespace-cdn.com/content/v1/68553a0b1f8c0d662c3653da/ef3aadb6-5564-4d20-9056-fd31da943008/sunset-1227768_1920.jpg',
  },
]
</script>
