<template>
  <div>
    <h1 class="text-2xl font-semibold">{{ project.name }}</h1>
  </div>
  <h2 class="text-lg text-gray-600">{{ project.description }}</h2>
</template>

<script setup>
const {id} = useRoute().params;

const {
  data: project,
  status,
  error,
} = await useFetch(
  `https://66edc832380821644cddfb25.mockapi.io/projects/${id}`
);
useHead({
  title: project.value.name,
});
console.log(project.value);
</script>
