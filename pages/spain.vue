<template>
  <div>
    <!-- Hero -->
    <section class="relative h-[60vh] min-h-[420px] flex items-end overflow-hidden">
      <div
        class="absolute inset-0 bg-cover bg-center"
        style="background-image: url('https://images.squarespace-cdn.com/content/v1/68553a0b1f8c0d662c3653da/ef3aadb6-5564-4d20-9056-fd31da943008/sunset-1227768_1920.jpg')"
      />
      <div class="absolute inset-0 bg-gradient-to-t from-charcoal via-charcoal/50 to-transparent" />
      <div class="relative z-10 max-w-7xl mx-auto px-6 lg:px-12 pb-16 w-full">
        <p class="section-label mb-3">Our Markets</p>
        <div class="w-10 h-px bg-gold mb-6" />
        <h1 class="font-serif text-5xl lg:text-6xl font-semibold text-white">Spain & Gibraltar</h1>
      </div>
    </section>

    <!-- Projects -->
    <section class="py-24">
      <div class="max-w-7xl mx-auto px-6 lg:px-12 space-y-32">
        <article v-for="(project, i) in projects" :key="project.id">
          <div class="grid md:grid-cols-2 gap-12 lg:gap-20 items-start" :class="i % 2 === 1 ? 'md:[&>*:first-child]:order-2' : ''">
            <div class="space-y-4">
              <img :src="project.images[0]" :alt="project.name" class="w-full aspect-[4/3] object-cover" />
              <img v-if="project.images[1]" :src="project.images[1]" :alt="`${project.name} interior`" class="w-2/3 aspect-video object-cover ml-auto" />
            </div>
            <div class="pt-4">
              <div class="flex flex-wrap gap-3 mb-6">
                <span class="text-xs uppercase tracking-widest text-gold border border-gold/40 px-3 py-1">{{ project.type }}</span>
                <span class="text-xs uppercase tracking-widest text-white/40 border border-white/10 px-3 py-1">{{ project.units }}</span>
                <span class="text-xs uppercase tracking-widest text-white/40 border border-white/10 px-3 py-1">{{ project.location }}</span>
              </div>
              <h2 class="font-serif text-3xl lg:text-4xl font-semibold text-white mb-6">{{ project.name }}</h2>
              <p class="text-white/60 leading-relaxed mb-8">{{ project.description }}</p>
              <div>
                <p class="section-label mb-4">Highlights</p>
                <ul class="grid grid-cols-2 gap-2">
                  <li v-for="h in project.highlights" :key="h" class="flex items-center gap-2 text-sm text-white/60">
                    <span class="w-1 h-1 rounded-full bg-gold flex-shrink-0" />
                    {{ h }}
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </article>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
useHead({ title: 'Spain & Gibraltar — Carolla Asset Management' })

const projects = [
  {
    id: 'the28',
    name: 'The 28',
    location: 'Sotogrande',
    images: [
      'https://images.squarespace-cdn.com/content/v1/68553a0b1f8c0d662c3653da/fb597e58-9b94-4861-b3da-78882526e81f/28.png',
      'https://images.squarespace-cdn.com/content/v1/68553a0b1f8c0d662c3653da/1750415886746-AX51RE87XD92ZYAY68DL/soto5.png',
    ],
    type: 'Luxury Townhouses',
    units: '28 Units',
    description: '"The 28" is a small gated development of 28 state-of-the-art town houses designed and built by experts in turnkey villas and luxury property developments in Marbella, Sotogrande, Miami, New York, and Milan. Each contemporary house will have 3 or 4 en-suite bedrooms, large family living areas, extensive terracing and its own private garaging. All will have their own private pool, with amazing sea views and are within easy walking distance to the best international school in Spain.',
    highlights: ['3–4 en-suite bedrooms', 'Private pool per unit', 'Sea views', 'High thermal efficiency', 'Photovoltaics & solar', 'Gated community'],
  },
  {
    id: 'villas',
    name: '12 Villas',
    location: 'Sotogrande Alto',
    images: [
      'https://images.squarespace-cdn.com/content/v1/68553a0b1f8c0d662c3653da/82d91360-38b2-4d42-8007-078399c01032/03+Final.JPG',
      'https://images.squarespace-cdn.com/content/v1/68553a0b1f8c0d662c3653da/1e61eda3-b6e5-4a92-8757-afd3d9cf6d55/BBQ.jpg',
    ],
    type: 'Luxury Villas',
    units: '12 Villas',
    description: 'This development site is located in the exclusive Sotogrande Alto area, with a gentle slope to the south, offering all plots views over the Almenara golf course and out to the Mediterranean. The concept is to create luxury villas on individual plots with the highest levels of security and leisure facilities for the exclusive use of the owners and their guests. Each villa will have a minimum of five bedrooms, large living rooms with high ceilings, and generous covered terraces with an adjacent private pool.',
    highlights: ['Minimum 5 bedrooms', 'Private pool & terrace', 'Golf course views', 'Mediterranean views', 'Natural light basement', 'Private entrance'],
  },
]
</script>
