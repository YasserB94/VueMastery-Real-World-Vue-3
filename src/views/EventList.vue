<script setup>
import { onMounted, ref } from 'vue';
import EventCard from '../components/EventCard.vue';
import EventService from "../services/EventService.js";
let events = ref([]);
let hasError = ref(false);
onMounted(async () => {
  try {
    const response = await EventService.getEvents();
    events.value = response.data;
    hasError.value=false;
  }catch (e){
    hasError.value=true;
  }
});
</script>

<template>
  <section class="space-y-2">
    <p v-show="hasError" class="text-2xl text-red-500">Oops something went wrong!</p>
    <ul>
      <li class="event-list">
        <EventCard
          v-for="(event, index) in events"
          :key="`${index}${event.title}`"
          :event="event"
        />
      </li>
    </ul>
  </section>
</template>
<style>
.event-list {
  @apply mx-auto grid items-center justify-center;
}
</style>
