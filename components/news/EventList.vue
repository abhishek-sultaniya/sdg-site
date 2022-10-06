<template>
  <div class="event-list">
    <div v-for="event in events" :key="event.id">
      <hr />
      <SingleEvent :event="event" />
      <br />
    </div>
    <hr />
  </div>
</template>

<script>
import { defineComponent } from '@nuxtjs/composition-api';
import SingleEvent from './SingleEvent.vue';

export default defineComponent({
  components: { SingleEvent },
  props: {
    events: {
      type: Array,
      default: () => [],
    },
  },
});
</script>

<style></style>
