<script setup>
import image from '~/imgs/goldT.png'
</script>

<template>
  <section class="flex bg-teal-900 flex-wrap items-center justify-between px-4 py-16 md:px-8">
    <!-- Left Column: Title and Description -->
    <div class="mb-8 w-full md:mb-0 md:w-1/2">
      <h1 class="mb-4 text-3xl text-white font-bold md:text-4xl">
        {{ $t('story.title') }}
      </h1>
      <p class="text-lg">
        {{ $t('story.desc') }}
      </p>
    </div>

    <!-- Right Column: Image -->
    <div class="w-full flex justify-center md:w-1/2">
      <img class="h-auto w-sm rounded-lg md:w-lg" :src="image" alt="Story Image">
    </div>
  </section>
</template>
