<script setup>
import { onMounted, ref } from 'vue';
import EventService from '../services/EventService.js';
const props = defineProps({
  id: String,
});
let event = ref({});
onMounted(async () => {
  try {
    const response = await EventService.getEvent(props.id);
    event.value = response.data;
  } catch (e) {
    //Try Again
  }
});
</script>

<template>
  <section class="event-details" v-show="event.title">
    <h1>{{ event.title }}</h1>
    <p class="time">
      {{ event.time }} on {{ event.date }} @ {{ event.location }}
    </p>
    <p>{{ event.description }}</p>
  </section>
</template>
<style scoped>
.event-details {
  @apply grid items-center justify-center space-y-4 text-center;
}
.event-details h1 {
  @apply mb-2 text-4xl;
}
.event-details .time {
  @apply text-sm opacity-90;
}
</style>
