<template>
  <article
    class="prose dark:prose-invert prose-img:text-center prose-img:rounded-lg prose-img:mx-auto"
  >
    <ContentDoc />
  </article>
</template>

<script setup>
const route = useRoute();
console.log(route.params.slug);
useHead({
  title: route.params.slug[0],
});
</script>
