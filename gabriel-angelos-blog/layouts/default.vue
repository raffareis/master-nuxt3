<template>
  <div class="container mx-auto md:max-w-2xl lg:max-w-4xl">
    <header class="flex justify-between items-center mt-5 mb-5">
      <div class="flex items-center space-x-12">
        <NuxtLink to="/" class="text-xl font-semibold p-2 hover:bg-gray-200">
          Gabriel Angelos
        </NuxtLink>
        <Menu />
      </div>
      <ClientOnly>
        <ColorModeSelector />
      </ClientOnly>
    </header>
    <main class="p-2 mt-10 mx-auto">
      <slot />
    </main>
  </div>
</template>

<script setup>
useSeoMeta({
  title: "Gabriel's Portfolio",
  description:
    'Gabriel Angelos, Captain of the Blood Ravens 3rd Company. Savior of Tartarus, bane of the Black Legion, servant of the Emperor.',
  ogTitle: "Gabriel's Portfolio",
  ogDescription:
    'Gabriel Angelos, Captain of the Blood Ravens 3rd Company. Savior of Tartarus, bane of the Black Legion, servant of the Emperor.',
  ogImage: '/Gabriel_Angelos_Portrait.webp',
  ogUrl: 'https://warhammer40k.fandom.com/wiki/Gabriel_Angelos',
  twitterTitle: "Gabriel's Portfolio",
  twitterDescription:
    'Gabriel Angelos, Captain of the Blood Ravens 3rd Company. Savior of Tartarus, bane of the Black Legion, servant of the Emperor.',
  twitterImage: '/Gabriel_Angelos_Portrait.webp',
  twitterCard: 'summary',
});

useHead({
  titleTemplate: '%s | Gabriel Angelos',
  htmlAttrs: {
    lang: 'en',
  },
  link: [
    {
      rel: 'icon',
      type: 'image/png',
      href: '/Gabriel_Angelos_Portrait.webp',
    },
    {rel: 'preconnect', href: 'https://fonts.googleapis.com'},
    {rel: 'preconnect', href: 'https://fonts.gstatic.com', crossorigin: ''},
    {
      rel: 'stylesheet',
      href: 'https://fonts.googleapis.com/css2?family=Roboto+Slab:wght@100..900&display=swap',
    },
  ],
});

// const colorMode = useColorMode();
</script>

<style>
body {
  font-family: 'Roboto Slab', serif;
}

body {
  @apply bg-gray-100 dark:bg-gray-900 text-gray-900 dark:text-gray-100;
}
</style>
