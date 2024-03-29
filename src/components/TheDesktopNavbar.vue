<script setup>
import { useI18n } from 'vue-i18n'
import { ref } from 'vue'
import { availableLocales, loadLanguageAsync } from '~/modules/i18n'

const { t, locale } = useI18n()
const isHovered = ref(false)
const NAV_ITEMS = [
  { label: t('nav.item1'), route: '/' },
  { label: t('nav.item2'), route: '/story' },
  { label: t('nav.item3'), route: '/services' },
  { label: t('nav.item5'), route: '/team' },
]

function callPhoneNumber() {
  const phoneNumber = '+1234567890'
  window.location.href = `tel:${phoneNumber}`
}

async function toggleLocales() {
  const newLocale = availableLocales[(availableLocales.indexOf(locale.value) + 1) % availableLocales.length]
  await loadLanguageAsync(newLocale)
  locale.value = newLocale
}
</script>

<template>
  <nav class="sticky top-0 z-50 mx-auto items-center rounded-full bg-teal-950 px-6 py-1 text-xl container md:flex md:items-center md:justify-between">
    <!-- Logo Section -->
    <div>
      <TheLogo w-20 />
    </div>
    <!-- Items Section -->
    <div class="flex flex-row cursor-pointer items-center text-2xl font-mono md:text-xl">
      <router-link
        v-for="item in NAV_ITEMS"
        :key="item.label"
        :to="item.route"
        class="cursor-pointed rounded-xl px-4 py-1 text-amber-100 transition-all duration-400 hover:scale-110"
        :class="{ ' font-bold z-10 text-cyan-950 bg-amber-100': $route.path === item.route }"
      >
        <span>{{ item.label }} </span>
      </router-link>
    </div>
    <!-- Button Section -->
    <div class="flex items-center justify-center gap-4">
      <button
        class="relative overflow-hidden rounded-xl bg-amber-100 px-1 py-1 text-teal-950 font-bold transition-all duration-700 md:block focus:bg-amber-200 focus:outline-none"
        :class="{ 'w-10': !isHovered, 'w-70': isHovered }"
        @mouseenter="isHovered = true"
        @mouseleave="isHovered = false"
        @click="callPhoneNumber"
      >
        <div flex>
          <div i-carbon:phone-filled text-xl class="mr-2" />
          <span :class="{ 'opacity-0': !isHovered, 'opacity-100': isHovered }" class="absolute left-1/2 top-1/2 transform whitespace-nowrap -translate-x-1/2 -translate-y-1/2">Programeaza-te</span>
        </div>
      </button>

      <!-- Language Dropdown -->
      <div class="cursor-pointer py-2 text-2xl text-amber-100" @click="toggleLocales()">
        <div class="cursor-pointer transition-all duration-400 hover:scale-110" i-carbon-language />
      </div>
    </div>
  </nav>
  <hr border-sm mt-2 min-w-screen border-amber-100>
</template>
