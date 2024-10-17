<template>
  <section v-if="status === 'pending'">
    <p>Loading...</p>
  </section>
  <section v-else-if="status === 'error'">
    <p>Error: {{ error.message }}</p>
  </section>
  <section v-else>
    <ul class="grid grid-cols-1 gap-4">
      <li
        v-for="post in posts"
        :key="post._path"
        class="p-4 rounded-sm shadow-md border border-gray-200 hover:bg-gray-300 dark:hover:bg-gray-700 transition-all duration-300"
      >
        <NuxtLink :to="post._path">
          <NuxtImg
            :src="post.image?.src"
            :alt="post.image?.alt"
            class="w-full h-40 object-cover"
          />
          <h3 class="text-lg font-semibold">{{ post.title }}</h3>
          <p class="text-gray-600 dark:text-gray-400">
            {{ post.description }}
          </p>
        </NuxtLink>
      </li>
    </ul>
  </section>
</template>

<script setup>
useHead({
  title: 'Blog',
});

const {
  data: posts,
  status,
  error,
} = await useAsyncData('posts', () =>
  queryContent('/blog').only(['title', 'description', '_path', 'image']).find()
);
</script>
