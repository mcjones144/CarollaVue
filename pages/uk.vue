<template>
  <div>
    <!-- Hero -->
    <section class="relative h-[60vh] min-h-[420px] flex items-end overflow-hidden">
      <div
        class="absolute inset-0 bg-cover bg-center"
        style="background-image: url('https://images.squarespace-cdn.com/content/v1/68553a0b1f8c0d662c3653da/1750599254564-SNAI0WMLL4GDAQYY2DAX/unsplash-image-q140lHKzXZY.jpg')"
      />
      <div class="absolute inset-0 bg-gradient-to-t from-charcoal via-charcoal/50 to-transparent" />
      <div class="relative z-10 max-w-7xl mx-auto px-6 lg:px-12 pb-16 w-full">
        <p class="section-label mb-3">Our Markets</p>
        <div class="w-10 h-px bg-gold mb-6" />
        <h1 class="font-serif text-5xl lg:text-6xl font-semibold text-white">United Kingdom</h1>
      </div>
    </section>

    <!-- Projects -->
    <section class="py-24">
      <div class="max-w-7xl mx-auto px-6 lg:px-12 space-y-24">
        <article
          v-for="(project, i) in projects"
          :key="project.id"
          class="grid md:grid-cols-2 gap-12 lg:gap-20 items-center"
          :class="i % 2 === 1 ? 'md:[&>*:first-child]:order-2' : ''"
        >
          <div class="overflow-hidden">
            <img :src="project.img" :alt="project.name" class="w-full aspect-[4/3] object-cover hover:scale-105 transition-transform duration-700" />
          </div>
          <div>
            <div class="flex flex-wrap gap-3 mb-6">
              <span class="text-xs uppercase tracking-widest text-gold border border-gold/40 px-3 py-1">{{ project.status }}</span>
              <span class="text-xs uppercase tracking-widest text-white/40 border border-white/10 px-3 py-1">{{ project.type }}</span>
            </div>
            <h2 class="font-serif text-3xl lg:text-4xl font-semibold text-white mb-6">{{ project.name }}</h2>
            <p class="text-white/60 leading-relaxed mb-4">{{ project.description }}</p>
            <p class="text-gold/80 text-sm italic">{{ project.detail }}</p>
          </div>
        </article>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
useHead({ title: 'United Kingdom — Carolla Asset Management' })

const projects = [
  {
    id: 'acton',
    name: 'Acton – London',
    img: 'https://images.squarespace-cdn.com/content/v1/68553a0b1f8c0d662c3653da/1750415887645-4TN03HJ0SZVNS1RWJS09/acton.png',
    status: 'Planning Approved',
    type: 'Student Accommodation / Cultural Centre',
    description: "Carolla have been in a Joint Venture with the Charity holding the freehold of the Caspian Cultural Centre, in Acton, West London since 2019, having agreed to develop a new cultural centre for the Charity on their behalf. Carolla's solution was to design a building that would provide 105 student rooms over six floors above the new centre, to be held on a long-term ground lease. The project was given unanimous support by the Planning Committee and was approved in early 2023.",
    detail: 'Work is due to start on site late in 2025.',
  },
  {
    id: 'wheatley',
    name: 'Wheatley – Oxford',
    img: 'https://images.squarespace-cdn.com/content/v1/68553a0b1f8c0d662c3653da/1750415887649-G1O3UWWSMTNBNYMOSGI0/wheatly.png',
    status: 'Completed',
    type: 'Workforce Accommodation / Training Centre',
    description: "With our joint venture partners at Oxford Equity Group we operated an onsite induction and training centre on behalf of EKFB, part of the HS2 Delivery Team. We provided 156 serviced workforce accommodation rooms and facilities, becoming one of HS2's accredited suppliers. We opened the facility in Spring 2022 having negotiated terms with Oxford Brookes University.",
    detail: 'The facility closed in Autumn 2024 when the University completed their disposal of the site. We are currently searching for an alternative site to continue this partnership.',
  },
]
</script>
