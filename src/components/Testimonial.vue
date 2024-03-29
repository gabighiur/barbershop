<script>
export default {
  data() {
    return {
      testimonials: [
        { name: 'Kenzie Edgar', avatar: 'https://i.pravatar.cc/100?img=1', text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos sunt ratione dolor exercitationem minima quas itaque saepe quasi architecto vel! Accusantium, vero sint recusandae cum tempora nemo commodi soluta deleniti.' },
        { name: 'Stevie Tifft', avatar: 'https://i.pravatar.cc/100?img=2', text: 'Lorem ipsum, dolor sit amet, consectetur adipisicing elit. Dolore quod necessitatibus, labore sapiente, est, dignissimos ullam error ipsam sint quam tempora vel.' },
        { name: 'Tommie Ewart', avatar: 'https://i.pravatar.cc/100?img=3', text: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vitae, obcaecati ullam excepturi dicta error deleniti sequi.' },
        { name: 'Charlie Howse', avatar: 'https://i.pravatar.cc/100?img=4', text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Architecto inventore voluptatum nostrum atque, corrupti, vitae esse id accusamus dignissimos neque reprehenderit natus, hic sequi itaque dicta nisi voluptatem! Culpa, iusto.' },
        { name: 'Nevada Herbertson', avatar: 'https://i.pravatar.cc/100?img=5', text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Nobis, voluptatem porro obcaecati dicta, quibusdam sunt ipsum, laboriosam nostrum facere exercitationem pariatur deserunt tempora molestiae assumenda nesciunt alias eius? Illo, autem!' },
        { name: 'Kris Stanton', avatar: 'https://i.pravatar.cc/100?img=6', text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem iusto, explicabo, cupiditate quas totam!' },
        { name: 'Brendan Donoghue', avatar: 'https://i.pravatar.cc/100?img=7', text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Velit temporibus alias nemo eius voluptate veniam dignissimos dolorem, corporis magni consequatur ad incidunt impedit libero esse sunt officia aperiam doloremque illo!' },
        { name: 'Taylor Craigie', avatar: 'https://i.pravatar.cc/100?img=8', text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Velit temporibus alias nemo eius voluptate veniam dignissimos dolorem, corporis magni consequatur ad incidunt impedit libero esse sunt officia aperiam doloremque illo!' },
        { name: 'Ryan Murdock', avatar: 'https://i.pravatar.cc/100?img=9', text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Velit temporibus alias nemo eius voluptate veniam dignissimos dolorem, corporis magni consequatur ad incidunt impedit libero esse sunt officia aperiam doloremque illo!' },
      ],
      showAllTestimonials: false,
    }
  },
  computed: {
    displayedTestimonials() {
      return this.showAllTestimonials ? this.testimonials : this.testimonials.slice(0, 3)
    },
  },
}
</script>

<template>
  <div class="mx-auto max-w-6xl w-full px-5 py-16 text-amber-100 md:py-24">
    <div class="mx-auto max-w-xl text-center">
      <h1 class="mb-5 text-4xl text-white font-bold md:text-5xl">
        Ce spun clienții noștri.
      </h1>
      <h3 class="mb-5 text-lg font-light md:text-xl">
        Lorem ipsum dolor sit amet consectetur adipisicing elit.
      </h3>
      <div class="mb-10 text-center">
        <span class="ml-1 inline-block h-1 w-1 rounded-full bg-amber-200" />
        <span class="ml-1 inline-block h-1 w-3 rounded-full bg-amber-200" />
        <span class="inline-block h-1 w-40 rounded-full bg-amber-200" />
        <span class="ml-1 inline-block h-1 w-3 rounded-full bg-amber-200" />
        <span class="ml-1 inline-block h-1 w-1 rounded-full bg-amber-200" />
      </div>
    </div>
    <div class="grid grid-cols-1 gap-6 lg:grid-cols-3 md:grid-cols-2">
      <div v-for="(testimonial, index) in displayedTestimonials" :key="index">
        <div class="border border-gray-200 rounded-lg bg-white p-5 text-gray-800 font-light">
          <div class="mb-4 flex items-center">
            <div class="h-10 w-10 overflow-hidden border border-gray-200 rounded-full bg-gray-50">
              <img :src="testimonial.avatar" :alt="`Avatar ${index}`" class="h-full w-full rounded-full object-cover object-center">
            </div>
            <div class="flex-grow pl-3">
              <h6 class="text-sm text-gray-600 font-bold uppercase">
                {{ testimonial.name }}
              </h6>
            </div>
          </div>
          <div>
            <p class="text-sm leading-tight">
              <span class="mr-1 text-lg text-gray-400 font-bold leading-none italic">"</span>{{ testimonial.text }}<span class="ml-1 text-lg text-gray-400 font-bold leading-none italic">"</span>
            </p>
          </div>
        </div>
      </div>
    </div>
    <button v-if="!showAllTestimonials" class="focus:shadow-outline mx-auto mt-8 block rounded bg-amber-100 px-4 py-2 text-teal-950 font-bold hover:bg-amber-200 focus:outline-none" @click="showAllTestimonials = true">
      Vezi mai multe recenzii
    </button>
    <button v-else class="focus:shadow-outline mx-auto mt-8 block rounded bg-amber-100 px-4 py-2 text-teal-950 font-bold hover:bg-amber-200 focus:outline-none" @click="showAllTestimonials = false">
      Ascunde recenziile
    </button>
  </div>
</template>

<style scoped>
/* Add your component-specific styles here */
</style>
