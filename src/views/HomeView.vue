<template>
  <h1>Events For Good</h1>
  <div class="events">
    <EventCard v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>

<script>
// @ is an alias to /src
import EventCard from "@/components/EventCard.vue";

export default {
  name: "HomeView",
  components: {
    EventCard,
  },
  data() {
    return {
      events: [
        {
          id: 5928101,
          category: "animal welfare",
          title: "Cat Adoption Day",
          description: "Find your new feline friend at this event.",
          location: "Meow Town",
          date: "January 28, 2022",
          time: "12:00",
          petsAllowed: true,
          organizer: "Kay Laydee",
        },
        {
          id: 4582797,
          category: "food",
          title: "Community Gardening",
          description:
            "Join us for a day of community gardening and fresh produce.",
          location: "Greenfield Park",
          date: "February 12, 2022",
          time: "10:00",
          petsAllowed: true,
          organizer: "Fern Pollin",
        },
        {
          id: 8419988,
          category: "sustainability",
          title: "Beach Cleanup",
          description:
            "Join us for a community beach cleanup and help protect our environment.",
          location: "Sunny Beach",
          date: "March 15, 2022",
          time: "09:00",
          petsAllowed: false,
          organizer: "Carey Wales",
        },
      ],
    };
  },
};
</script>

<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
