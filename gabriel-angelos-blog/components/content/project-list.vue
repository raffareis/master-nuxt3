<template>
  <section v-if="status === 'pending'">
    <p>Loading...</p>
  </section>
  <section v-else-if="status === 'error'">
    <p>Error: {{ error.message }}</p>
  </section>
  <section v-else class="not-prose font-mono">
    <div class="grid grid-cols-3 gap-8 text-gray-400 text-sm mb-2">
      <div class="text-lg font-semibold">Name</div>
      <div class="text-lg font-semibold">Description</div>
      <div class="text-lg font-semibold">Created At</div>
    </div>
    <ul>
      <li v-for="project in projects" :key="project.id">
        <NuxtLink
          :to="`/projects/${project.id}`"
          class="grid grid-cols-3 gap-8 hover:bg-gray-200 dark:hover:bg-gray-800 py-2 border-b border-gray-200 dark:border-gray-800"
        >
          <div>{{ project.name }}</div>
          <div>{{ project.description }}</div>
          <div>{{ project.createdAt }}</div>
        </NuxtLink>
      </li>
    </ul>
  </section>
</template>

<script setup>
useHead({
  title: 'My Projects',
});

const {
  data: projects,
  status,
  error,
} = await useFetch('https://66edc832380821644cddfb25.mockapi.io/projects');
</script>

<style scoped>
.column {
  @apply flex items-center space-x-8 py-2 border-b border-gray-200 dark:border-gray-800;
}
</style>
