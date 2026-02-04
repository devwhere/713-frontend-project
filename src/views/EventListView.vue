<script setup lang="ts">
import { ref } from 'vue'
import EventCard from '@/components/EventCard.vue'
const events = ref([
  { id: 1, name: 'Event 1' },
  { id: 2, name: 'Event 2' },
  { id: 3, name: 'Event 3' },
])
</script>

<template>
  <div></div>
  <div class="event-list">
    <div v-if="events.length === 0">No Events</div>
    <div v-else-if="events.length === 1">Only one event</div>
    <div v-else>
      <EventCard v-for="event in events" :key="event.id" :name="event.name" />
    </div>
  </div>
</template>

<style scoped>
.event-list {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
