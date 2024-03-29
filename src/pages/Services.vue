<script setup>
import img from '~/imgs/preturi.png'
</script>

<template>
  <section class="flex items-center justify-center bg-teal-950 p-8">
    <div class="flex flex-col items-center border-2 border-amber-200 p-8 text-center">
      <h1 mb-4 text-2xl text-amber-100 font-bold md:text-4xl>
        {{ $t('services.price') }}
      </h1>
      <img :src="img" class="w-sm">
    </div>
  </section>
</template>
