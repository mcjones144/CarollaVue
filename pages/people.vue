<template>
  <div>
    <!-- Hero -->
    <section class="relative h-[60vh] min-h-[420px] flex items-end overflow-hidden">
      <div
        class="absolute inset-0 bg-cover bg-center"
        :style="{ backgroundImage: `url(${peopleHero})` }"
      />
      <div class="absolute inset-0 bg-gradient-to-t from-charcoal via-charcoal/50 to-transparent" />
      <div class="relative z-10 max-w-7xl mx-auto px-6 lg:px-12 pb-16 w-full">
        <p class="section-label mb-3">The Team</p>
        <div class="w-10 h-px bg-gold mb-6" />
        <h1 class="font-serif text-5xl lg:text-6xl font-semibold text-white">Our People</h1>
        <p class="text-white/50 mt-4 max-w-xl leading-relaxed">
          A team of experienced property, finance and technology professionals united by a shared commitment to delivering value in partnership.
        </p>
      </div>
    </section>

    <!-- Team grid -->
    <section class="py-24">
      <div class="max-w-7xl mx-auto px-6 lg:px-12">
        <div class="grid grid-cols-2 md:grid-cols-4 gap-6 lg:gap-8">
          <button
            v-for="member in team"
            :key="member.name"
            class="group text-left"
            @click="selectedMember = member"
          >
            <div class="overflow-hidden mb-4 aspect-[3/4]">
              <img
                :src="member.img"
                :alt="member.name"
                class="w-full h-full object-cover object-top group-hover:scale-105 transition-transform duration-700"
              />
            </div>
            <p class="section-label mb-1">{{ member.role }}</p>
            <h2 class="font-serif text-lg text-white font-semibold group-hover:text-gold transition-colors">{{ member.name }}</h2>
          </button>
        </div>
      </div>
    </section>

    <!-- Modal -->
    <Transition name="fade">
      <div
        v-if="selectedMember"
        class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/70 backdrop-blur-sm"
        @click.self="selectedMember = null"
      >
        <div class="bg-charcoal-light border border-white/10 max-w-2xl w-full p-8 relative flex flex-col sm:flex-row gap-8">
          <!-- Close -->
          <button
            class="absolute top-4 right-4 text-white/40 hover:text-white transition-colors text-xl leading-none"
            @click="selectedMember = null"
          >
            ✕
          </button>

          <!-- Photo -->
          <div class="flex-shrink-0">
            <img
              :src="selectedMember.img"
              :alt="selectedMember.name"
              class="w-40 h-52 object-cover object-top"
            />
          </div>

          <!-- Text -->
          <div class="flex-1 pt-1">
            <p class="section-label mb-2">{{ selectedMember.role }}</p>
            <h2 class="font-serif text-2xl text-white font-semibold mb-4">{{ selectedMember.name }}</h2>
            <p class="text-white/60 leading-relaxed text-sm">{{ selectedMember.bio }}</p>
          </div>
        </div>
      </div>
    </Transition>
  </div>
</template>

<script setup lang="ts">
import peopleHero from '~/public/people-hero.jpg'

useHead({ title: 'People — Carolla Asset Management' })

const selectedMember = ref<typeof team[0] | null>(null)

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

<style scoped>
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.25s ease;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
}
</style>
