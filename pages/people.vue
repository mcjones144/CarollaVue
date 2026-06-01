<template>
  <div>
    <!-- Header -->
    <section class="pt-40 pb-20 bg-charcoal-light">
      <div class="max-w-7xl mx-auto px-6 lg:px-12">
        <p class="section-label mb-3">The Team</p>
        <div class="w-10 h-px bg-gold mb-6" />
        <h1 class="font-serif text-5xl lg:text-6xl font-semibold text-white">Our People</h1>
        <p class="text-white/50 mt-6 max-w-xl leading-relaxed">
          A team of experienced property, finance and technology professionals united by a shared commitment to delivering value in partnership.
        </p>
      </div>
    </section>

    <!-- Team grid -->
    <section class="py-24">
      <div class="max-w-7xl mx-auto px-6 lg:px-12">
        <div class="grid md:grid-cols-2 gap-16 lg:gap-20">
          <article v-for="member in team" :key="member.name" class="group">
            <div class="overflow-hidden mb-6 aspect-[3/4] max-w-xs">
              <img :src="member.img" :alt="member.name" class="w-full h-full object-cover object-top group-hover:scale-105 transition-transform duration-700" />
            </div>
            <p class="section-label mb-2">{{ member.role }}</p>
            <h2 class="font-serif text-2xl text-white font-semibold mb-4">{{ member.name }}</h2>
            <p class="text-white/55 leading-relaxed text-sm">{{ member.bio }}</p>
          </article>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
useHead({ title: 'People — Carolla Asset Management' })

const team = [
  {
    name: 'Christopher Jones',
    role: 'Co-Founder & Director',
    img: 'https://images.squarespace-cdn.com/content/v1/68553a0b1f8c0d662c3653da/fb5aaa77-a2de-4080-a105-45e0cd06bea3/dad.jpg',
    bio: "Chris is a seasoned British businessman with a diverse portfolio of directorships across multiple sectors, including asset management, property development and investment. Having been in property development for three decades, Chris's dedication and strategic vision in steering real estate projects towards successful conclusions brings drive and focus to the Carolla team.",
  },
  {
    name: 'Jim Craig',
    role: 'Co-Founder & Director',
    img: 'https://images.squarespace-cdn.com/content/v1/68553a0b1f8c0d662c3653da/f0c981e9-8268-44da-a7c6-65175cd4e2d6/image.png',
    bio: "Jim is a finance director with extensive experience in luxury property development in the UK and Spain. He has a proven track record of success in financial control, capital projects, programme management, start-up ventures and complex dispute resolution. With his hands-on approach and strong negotiating skills Jim has consistently delivered projects on time and on budget.",
  },
  {
    name: 'Andrew Hardy',
    role: 'Co-Founder & Director',
    img: 'https://images.squarespace-cdn.com/content/v1/68553a0b1f8c0d662c3653da/04289bde-b6e0-43c9-b274-3e732b2e5422/AJH+mugshot+2.JPG',
    bio: 'Andrew is a qualified Chartered Surveyor and has gained extensive commercial property experience working in Europe and The Middle & Far East with major international real estate organisations for over 30 years. Through his involvement in numerous successful projects across the globe, he has created an international network of real estate contacts which he now brings to the Carolla team.',
  },
  {
    name: 'Michael Jones',
    role: 'Associate Partner',
    img: 'https://images.squarespace-cdn.com/content/v1/68553a0b1f8c0d662c3653da/d1a9fde9-c405-46c6-b296-d0da2686dbac/me.jpg',
    bio: "Mikey joins the Carolla Team from a Fintech background, where he has spent over 10 years in Europe working on client payment applications. He was responsible for designing and implementing the appropriate systems, rolling these out and working hands-on with his team. His problem-solving and project-oriented approach fits in very well with Carolla's ethos.",
  },
]
</script>
