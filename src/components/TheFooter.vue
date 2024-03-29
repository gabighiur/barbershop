<script setup>
import Logo from '~/imgs/logow.png'
</script>

<template>
  <footer>
    <div class="mx-auto mb-8 px-8 py-8 container md:py-8">
      <div class="flex items-center justify-between lg:flex">
        <!-- Left section: Address and phone -->
        <div>
          <div class="flex items-center">
            <div i-carbon:location-filled class="mr-2 text-xl text-gray-600 dark:text-gray-400" />
            <span text-left>Bulevardul Theodor Pallady 1, București 032251</span>
          </div>
          <div class="mt-2 flex items-center">
            <div i-carbon:phone class="mr-2 text-xl text-gray-600 dark:text-gray-400" />
            <span>0728 797 179</span>
          </div>
          <div class="mt-2 flex items-center">
            <a href="https://www.instagram.com/goldman.barbershop/" target="_blank" rel="noopener noreferrer" class="mr-2">
              <div i-carbon:logo-instagram hover:text-amber-200 class="text-xl text-gray-600 dark:text-gray-400" />
            </a>
            <a href="https://www.facebook.com/p/Gold-Man-Barbershop-100075883749894/" target="_blank" rel="noopener noreferrer">
              <div i-carbon:logo-facebook class="text-xl text-gray-600 dark:text-gray-400 hover:text-amber-200" />
            </a>
          </div>
        </div>

        <!-- Right section: Social media icons -->
        <div class="flex items-center space-x-4">
          <img :src="Logo" class="mx-auto w-30" alt="Hyenas Transparent NFT">
        </div>
      </div>

      <!-- Copyright -->
      <hr class="my-4 border-gray-200 sm:mx-auto dark:border-gray-700">
      <p class="text-center text-sm text-gray-500 dark:text-gray-400">
        &copy;2023 <a href="#" class="hover:underline">GoldMan Barbershop</a>. {{ $t('footer.rights') }}.
      </p>
    </div>
  </footer>
</template>
