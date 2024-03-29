<script setup>
import videoClip from '~/imgs/header3.mp4'
function callPhoneNumber() {
  // Replace '1234567890' with your phone number
  const phoneNumber = '+1234567890'
  window.location.href = `tel:${phoneNumber}`
}
</script>

<template>
  <section class="relative min-h-screen flex flex-col items-center justify-center py-20">
    <!-- Content container -->
    <div class="relative z-10 text-center text-amber-100">
      <!-- Header text -->
      <h1 class="mb-4 text-6xl font-bold md:text-6xl">
        {{ $t('header.title') }}
      </h1>
      <h2 class="mb-8 text-2xl font-mono md:text-2xl">
        {{ $t('header.desc') }}
      </h2>

      <!-- Video background -->
      <div class="overflow-hidden">
        <video autoplay loop muted class="h-auto w-full opacity-60 md:w-4xl">
          <source :src="videoClip" type="video/mp4">
        </video>
      </div>

      <!-- Button -->
      <button class="mx-auto mt-4 rounded-full bg-amber-100 px-8 py-4 text-teal-950 font-bold md:mx-0 focus:bg-amber-200 hover:bg-amber-200 focus:outline-none" @click="callPhoneNumber">
        <div flex>
          <div i-carbon:phone-filled text-xl class="mr-2" />
          <span>Programeaza-te</span>
        </div>
      </button>
    </div>
  </section>
</template>
