<template>
  <div class="flex space-x-2 items-center">
    <div v-if="showNextMode" class="text-gray-500 text-xs">
      Change to {{ colorMode.preference === 'dark' ? 'Light' : 'Dark' }} Mode
    </div>
    <button
      @click="toggleColorMode"
      @mouseover="showNextMode = true"
      @mouseleave="showNextMode = false"
      class="text-gray-500 hover:text-gray-700 dark:hover:text-gray-300"
    >
      {{ modeIcons[colorMode.preference] }}
    </button>
  </div>
</template>

<script setup>
const colorMode = useColorMode();
const showNextMode = ref(false);
const modeIcons = {
  light: '🌕', // Full moon for light mode (representing day)
  dark: '🌛', // Half moon for dark mode (representing night)
};
const toggleColorMode = () => {
  colorMode.preference = colorMode.preference === 'dark' ? 'light' : 'dark';
};
</script>
