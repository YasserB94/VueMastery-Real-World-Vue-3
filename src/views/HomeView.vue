<script setup>
import EventCard from '../components/EventCard.vue';
const events = [
  {
    id: 5928101,
    category: 'animal welfare',
    title: 'Cat Adoption Day',
    description: 'Find your new feline friend at this event.',
    location: 'Meow Town',
    date: 'January 28, 2022',
    time: '12:00',
    petsAllowed: true,
    organizer: 'Kat Laydee',
  },
  {
    id: 4582797,
    category: 'food',
    title: 'Community Gardening',
    description: 'Join us as we tend to the community edible plants.',
    location: 'Flora City',
    date: 'March 14, 2022',
    time: '10:00',
    petsAllowed: true,
    organizer: 'Fern Pollin',
  },
  {
    id: 8419988,
    category: 'sustainability',
    title: 'Beach Cleanup',
    description: 'Help pick up trash along the shore.',
    location: 'Playa Del Carmen',
    date: 'July 22, 2022',
    time: '11:00',
    petsAllowed: false,
    organizer: 'Carey Wales',
  },
];
</script>

<template>
  <section class="space-y-2">
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
  .event-list{
    @apply mx-auto grid items-center justify-center
  }
</style>