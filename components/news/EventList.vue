<template>
  <div class="eventbody">
    <div class="eventlist">
      <div v-for="event in events" :key="event.id">
        <hr class="eventline" />
        <SingleEvent :event="event" />
        <br />
      </div>
      <hr class="eventline" />
    </div>
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

<style>
  .eventbody{
    background: url(/_next/static/media/grain-dark.9d5983e6.png) rgb(23, 15, 30);
  color: rgb(229, 225, 230);
  }
  .event{
    margin-top: 10px;
  }
.eventlist {
  width: 100%;
  margin-bottom: 0px;
  padding: 0px 64px;
}
.eventline{
  /* position: absolute;
    top: 0px;
    left: 0px;
    display: block;
    height: 1px;
    width: 100%; */
    background: linear-gradient(90deg, rgb(255, 215, 77) 0%, rgb(64, 221, 255) 50%, rgb(124, 127, 255) 100%);
}
</style>
