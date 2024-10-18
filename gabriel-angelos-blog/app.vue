<template>
  <div>
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
  </div>
</template>

<style>
.page-enter-active,
.page-leave-active {
  transition: all 0.3s ease-in-out;
}
.page-enter,
.page-leave-to {
  opacity: 0.5;
  filter: grayscale(100%) blur(0.1rem);
}
</style>
