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
        v-for="project in projects"
        :key="project.id"
        class="p-4 rounded-sm shadow-md border border-gray-200 hover:bg-gray-300 dark:hover:bg-gray-700 transition-all duration-300"
      >
        <NuxtLink :to="`/projects/${project.id}`">
          <h3 class="text-lg font-semibold">{{ project.name }}</h3>
          <p class="text-gray-600 dark:text-gray-400">
            {{ project.description }}
          </p>
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
console.log(status.value);
console.log(projects.value);
</script>
