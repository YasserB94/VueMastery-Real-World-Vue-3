<script setup>
import { useDark, useToggle } from '@vueuse/core';

const isDark = useDark();
const toggleDark = useToggle(isDark);
</script>

<template>
  <header>
    <button @click="toggleDark()">Dark Toggle</button>
    <nav>
      <router-link active-class="underline text-emerald-300" to="/">Events</router-link>
      <router-link active-class="underline text-emerald-300" to="/About">About</router-link>
    </nav>
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
  @apply flex w-full p-8;
}
header nav {
  @apply mx-4 ml-auto space-x-4;
}
header nav a {
  @apply decoration-emerald-800 duration-300 hover:text-emerald-300 hover:underline;
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
