<script setup lang="ts">
useHead({
  title: 'GoldMan BarberShop',
  meta: [
    {
      name: 'description',
      content: 'Aurul frumusetii masculine',
    },
    {
      name: 'theme-color',
      content: () => isDark.value ? '#00aba9' : '#ffffff',
    },
  ],
  link: [
    {
      rel: 'icon',
      type: 'image/png',
      href: () => preferredDark.value ? '/pwa-512x512.png' : '/pwa-512x512.png',
    },
  ],
})
</script>

<template>
  <RouterView />
</template>
