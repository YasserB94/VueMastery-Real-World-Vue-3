<script setup>
defineProps({
  event: {
    type: Object,
    required: true,
  },
});
</script>

<template>
  <div v-if="event.time && event.title" class="event-card">
    <span class="text-xs text-slate-600 dark:text-slate-300"
      >@{{ event.time }} on {{ event.date }}</span
    >
    <h4>{{ event.title }}</h4>
  </div>
</template>

<style scoped>
.event-card {
  @apply mb-1
  max-w-md
  cursor-pointer
  rounded-2xl
  border
  border-slate-800
  p-5
  transition
  duration-500
  hover:scale-x-110
  hover:shadow-lg
  dark:border-slate-50
  dark:bg-slate-800;
}
</style>
