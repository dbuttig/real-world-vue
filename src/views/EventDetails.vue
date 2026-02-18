<template>
  <div class="event-details" v-if="event">
    <h1>{{ event.title }}</h1>
    <p>{{ event.time }} on {{ event.date }} @ {{ event.location }}</p>
    <p>{{ event.description }}</p>
  </div>
  <div v-else class="event-loading">
    <p>Loading event...</p>
  </div>
</template>

<script>
import EventService from "@/services/EventService.js";
export default {
  props: ["id"],
  data() {
    return {
      event: null,
    };
  },
  created() {
    const routeId = this.$route && this.$route.params && this.$route.params.id;
    // console.log(
    //   "EventDetails created. route param id:",
    //   routeId,
    //   "prop id:",
    //   this.id
    // );
    const idToUse = this.id || routeId;
    if (!idToUse) {
      console.error("No id available for EventDetails (prop or route param)");
      return;
    }
    EventService.getEvent(idToUse)
      .then((response) => {
        console.log("EventService.getEvent response:", response);
        this.event = response.data;
      })
      .catch((error) => {
        console.error(
          "EventService.getEvent error:",
          error.response || error.message || error
        );
      });
  },
};
</script>
