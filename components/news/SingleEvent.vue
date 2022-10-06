<template>
  <div class="event">
    <nuxt-link :to="`/news/${event.id}`">
      <h3>{{ event.title }}</h3>
    </nuxt-link>
    <h3>Location: {{ event.location }}</h3>
    <h3>Date RSVP: {{ event.RSVP }}</h3>
    <p>{{ snippet }}</p>
  </div>
</template>

<script>
import { defineComponent, computed } from '@nuxtjs/composition-api';

export default defineComponent({
  props: {
    event: {
      type: Object,
      default: () => ({
        id: 1,
        title: 'Event Title',
        location: 'India',
        RSVP: 'Date',
        body: 'This is some long description of the event',
      }),
    },
  },
  setup(props) {
    const snippet = computed(() => {
      return props.event.body.substring(0, 40) + '...';
    });

    return { snippet };
  },
});
</script>

<style></style>
