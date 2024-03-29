<script setup>
</script>

<template>
  <section class="min-h-full flex items-center bg-teal-900 p-20 px-10 text-left lg:px-100 md:px-20">
    <div class="">
      <h6 class="text-amber-100 tracking-wide">
        {{ $t('story.sub') }}
      </h6>
      <h1 class="mb-4 text-3xl font-bold md:text-4xl">
        {{ $t('story.title') }}
      </h1>
      <p class="text-lg text-amber-100">
        {{ $t('story.desc') }}
      </p>
    </div>
  </section>
  <section class="bg-teal-950 px-10 py-20 lg:px-100 md:px-20">
    <div class="flex flex-col items-center justify-center md:flex-row md:justify-between">
      <!-- Text section -->
      <div class="mb-8 text-center md:mb-0 md:w-1/2 md:pr-10 md:text-left">
        <h2 class="mb-4 text-3xl text-white font-bold">
          Te așteptăm!
        </h2>
        <p class="text-lg text-white">
          Fă-ți programare ->
          <button class="text-white hover:text-amber-200" @click="callPhoneNumber">
            <div class="flex items-center">
              <div class="mr-1 text-xl" i-carbon:phone-filled />
            </div>
          </button>
          și te așteptăm cu drag la locație
        </p>
        <div class="flex items-center">
          <div class="mr-2 text-xl" i-carbon:location-filled />
          <span class="text-white">Bulevardul Theodor Pallady 1, București 032251</span>
        </div>
      </div>

      <!-- Location section -->
      <div class="barber-location md:w-1/2 md:pl-10">
        <!-- Google Maps embed code -->
        <iframe
          class="w-sm"
          width="600"
          height="450"
          frameborder="0"
          style="border:0"
          allowfullscreen
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2849.9755276641695!2d26.165323599999997!3d44.4131479!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x40b1ff15e8770ad9%3A0xbd94bbb30f9ce893!2sGold%20Man%20Barber%20Shop!5e0!3m2!1sen!2sro!4v1710363702435!5m2!1sen!2sro"
        />
      </div>
    </div>
  </section>
</template>
