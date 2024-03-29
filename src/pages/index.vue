<script setup lang="ts">
defineOptions({
  name: 'IndexPage',
})
</script>

<template>
  <TheHeader />
  <Story />
  <Testimonial />
  <Services />
  <Team />
</template>

<route lang="yaml">
meta:
  layout: home
</route>
