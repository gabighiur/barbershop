<!-- eslint-disable @stylistic/ts/comma-dangle -->
<script setup lang="ts">
import TheDesktopNavbar from './TheDesktopNavbar.vue'
import TheMobileNavbar from './TheMobileNavbar.vue'

const navbarComponent = ref(window.innerWidth > 768 ? TheDesktopNavbar : TheMobileNavbar)

window.addEventListener('resize', () => {
  navbarComponent.value = window.innerWidth > 768 ? TheDesktopNavbar : TheMobileNavbar
})
</script>

<template>
  <component :is="navbarComponent" />
</template>
