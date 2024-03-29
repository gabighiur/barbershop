<script setup>
</script>

<template>
  <section class="bg-teal-900">
    <div class="mx-auto max-w-screen-xl px-4 py-8 lg:px-6 lg:py-16">
      <div class="mx-auto mb-8 max-w-screen-sm text-center lg:mb-16">
        <h2 class="mb-4 text-4xl text-gray-900 font-extrabold tracking-tight dark:text-white">
          {{ $t('team.title') }}
        </h2>
        <p class="text-gray-500 font-light lg:mb-16 sm:text-xl dark:text-gray-400">
          {{ $t('team.desc') }}
        </p>
      </div>
      <div class="grid mb-6 gap-8 md:grid-cols-2 lg:mb-16">
        <div class="items-center border-gray-700 rounded-lg bg-teal-950 shadow sm:flex">
          <a href="#">
            <img class="w-full rounded-lg sm:rounded-none sm:rounded-l-lg" src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/avatars/bonnie-green.png" alt="Bonnie Avatar">
          </a>
          <div class="p-5">
            <h3 class="text-xl text-white font-bold tracking-tight">
              <a href="#">Bonnie Green</a>
            </h3>

            <p class="mb-4 mt-3 text-gray-500 font-light dark:text-gray-400">
              Bonnie drives the technical strategy of the flowbite platform and brand.
            </p>
          </div>
        </div>
        <div class="items-center border-gray-700 rounded-lg bg-teal-950 shadow sm:flex">
          <a href="#">
            <img class="w-full rounded-lg sm:rounded-none sm:rounded-l-lg" src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/avatars/jese-leos.png" alt="Jese Avatar">
          </a>
          <div class="p-5">
            <h3 class="text-xl text-gray-900 font-bold tracking-tight dark:text-white">
              <a href="#">Jese Leos</a>
            </h3>

            <p class="mb-4 mt-3 text-gray-500 font-light dark:text-gray-400">
              Jese drives the technical strategy of the flowbite platform and brand.
            </p>
          </div>
        </div>
        <div class="items-center border-gray-700 rounded-lg bg-teal-950 shadow sm:flex">
          <a href="#">
            <img class="w-full rounded-lg sm:rounded-none sm:rounded-l-lg" src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/avatars/michael-gouch.png" alt="Michael Avatar">
          </a>
          <div class="p-5">
            <h3 class="text-xl text-gray-900 font-bold tracking-tight dark:text-white">
              <a href="#">Michael Gough</a>
            </h3>

            <p class="mb-4 mt-3 text-gray-500 font-light dark:text-gray-400">
              Michael drives the technical strategy of the flowbite platform and brand.
            </p>
          </div>
        </div>
        <div class="items-center border-gray-700 rounded-lg bg-teal-950 shadow sm:flex">
          <a href="#">
            <img class="w-full rounded-lg sm:rounded-none sm:rounded-l-lg" src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/avatars/sofia-mcguire.png" alt="Sofia Avatar">
          </a>
          <div class="p-5">
            <h3 class="text-xl text-gray-900 font-bold tracking-tight dark:text-white">
              <a href="#">Lana Byrd</a>
            </h3>

            <p class="mb-4 mt-3 text-gray-500 font-light dark:text-gray-400">
              Lana drives the technical strategy of the flowbite platform and brand.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
