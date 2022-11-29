<script setup>
import { useDark, useToggle } from '@vueuse/core';

const isDark = useDark();
const toggleDark = useToggle(isDark);

</script>

<template>
  <header>
    <button @click="toggleDark()">Dark Toggle</button>
  </header>
  <main>
    <slot />
  </main>
  <footer>
    <p>Hi Mom!</p>
  </footer>
</template>

<style scoped>
header {
  @apply flex w-full justify-between p-8;
}
header button {
  @apply rounded-2xl border bg-transparent p-2;
}
main {
  @apply w-full;
}
footer {
  @apply w-full text-center;
}
</style>
