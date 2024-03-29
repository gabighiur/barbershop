<script setup lang="ts">
import { useI18n } from 'vue-i18n'
import { computed, ref } from 'vue'
import { availableLocales, loadLanguageAsync } from '~/modules/i18n'

const { t, locale } = useI18n()
const menuOpen = ref(false)
const hamburgerLine = 'h-0 w-6 border-t-4 rounded border-amber-100 mt-1'

const HOME = { label: t('nav.item1'), route: '/', section: '' }
const STORY = { label: t('nav.item2'), route: '/story', section: '' }
const SERVICES = { label: t('nav.item3'), route: '/services', section: '' }
const ABOUT = { label: t('nav.item5'), route: '/about', section: '' }

const socialLinks = [
  { name: 'GitHub', icon: 'i-carbon-logo-facebook', link: 'https://www.facebook.com/p/Gold-Man-Barbershop-100075883749894/', label: 'socials.github' },
  { name: 'Instagram', icon: 'i-carbon-logo-instagram', link: 'https://www.instagram.com/goldman.barbershop/', label: 'socials.instagram' },
]

async function toggleLocales() {
  const locales = availableLocales
  const newLocale = locales[(locales.indexOf(locale.value) + 1) % locales.length]
  await loadLanguageAsync(newLocale)
  locale.value = newLocale
}

interface MenuItem {
  label: string
  route: string
  section: string
}

const nonHamburgerItems: MenuItem[] = computed(() => {
  return [HOME, STORY, SERVICES, ABOUT]
})

const mobileMenuItems: MenuItem[] = computed(() => {
  return [HOME, STORY, SERVICES, ABOUT]
})

function callPhoneNumber() {
  const phoneNumber = '+1234567890'
  window.location.href = `tel:${phoneNumber}`
}
</script>

<template>
  <nav :class="{ ' z-50 sticky top-0 max-h-20 overflow-hidden': !menuOpen, 'z-50 sticky top-0 transition-all duration-600 ease-in': menuOpen }" class="flex items-center justify-between bg-teal-950 p-4">
    <!-- Non-Hamburger Menu Items -->
    <div class="gap-4 text-amber-100 md:flex">
      <router-link
        v-for="item in nonHamburgerItems"
        :key="item.label"
        :to="item.route"
        class="px-4 py-2 text-2xl text-amber-100"
        :class="{ 'font-bold text-cyan-950 bg-cyan-100 rounded-full': $route.path === item.route }"
      >
        {{ item.label }}
      </router-link>
    </div>

    <!-- Mobile Navbar -->
    <transition name="fade">
      <div v-if="menuOpen" class="fade-content rounded-r-b fixed left-0 top-0 h-full w-full flex flex-row items-center justify-center bg-teal-900 p-8 px-8 text-left text-4xl">
        <!-- Left Section: Menu Items, Button, Language Dropdown, Social Links -->
        <div class="flex flex-col items-center justify-center">
          <!-- Mobile Menu Items -->
          <div flex flex-col items-center justify-center>
            <router-link
              v-for="item in mobileMenuItems"
              :key="item.label"
              :to="item.route"
              class="flex py-2 text-4xl text-amber-100 hover:scale-110"
            >
              {{ item.label }}
            </router-link>
          </div>
          <!-- Button -->
          <button class="gap-2 whitespace-nowrap rounded-xl bg-amber-100 px-4 py-1 text-2xl text-teal-950 font-bold focus:bg-amber-200 hover:bg-amber-200 focus:outline-none" @click="callPhoneNumber">
            <div flex items-center gap-4>
              <div i-carbon:phone-filled class="" />
              <span>Programeaza-te</span>
            </div>
          </button>
          <!-- Language Dropdown -->
          <div class="py-2 text-2xl text-amber-100" @click="toggleLocales()">
            <div flex flex-row items-center gap-4 icon-btn>
              <div class="cursor-pointer" i-carbon-language />
              <span>Change language</span>
            </div>
          </div>
          <!-- Social Links -->
          <div class="flex items-center md:hidden space-x-4">
            <a v-for="socialLink in socialLinks" :key="socialLink.name" :href="socialLink.link" target="_blank" rel="noopener noreferrer">
              <div :class="socialLink.icon" class="text-2xl icon-btn" />
            </a>
          </div>
          <hr w-sm border-1 border-amber-100>
          <div class="mb-4 mt-20 w-30 opacity-30">
            <TheLogo />
          </div>
        </div>
      </div>
    </transition>

    <!-- Logo outside the menu -->
    <div>
      <TheLogo w-20 />
    </div>

    <!-- Hamburger Button -->
    <button class="group h-11 w-11 flex flex-col items-end justify-center md:hidden" @click="menuOpen = !menuOpen">
      <!-- First Hamburger Line -->
      <div :class="`${hamburgerLine} ${menuOpen ? 'rotate-45 translate-y-1 opacity-100 group-hover:opacity-100 transition-transform duration-300' : 'opacity-100 group-hover:opacity-100'}`" />
      <!-- Second Hamburger Line -->
      <div :class="`${hamburgerLine} ${menuOpen ? 'opacity-0' : 'opacity-100 group-hover:opacity-100'}`" />
      <!-- Third Hamburger Line -->
      <div :class="`${hamburgerLine} ${menuOpen ? '-rotate-45 -translate-y-2 opacity-100 group-hover:opacity-100 transition-transform duration-300' : 'opacity-100 group-hover:opacity-100'}`" />
    </button>
  </nav>
  <hr border-sm mt-2 min-w-screen border-amber-100>
</template>

<style scoped>
.fade-content {
  transition:
    opacity 0.5s,
    transform 0.5s;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
  transform: translateY(-50px);
}
</style>
