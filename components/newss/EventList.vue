<template>
  <div class="event-list">
      
    <div v-for="event in events" :key="event.id">
      <!-- <h3>{{event.title}}</h3> -->
      <hr/>
      <SingleEvent :event="event" />
      <br/>
    </div>
    <hr/>
  </div>
</template>
  
  <script>
  import { onMounted, onUnmounted, onUpdated } from 'vue' // eslint-disable-line
  
  // component imports
  import SingleEvent from './SingleEvent.vue'
  
  export default {
    components: { SingleEvent },
    props: ['events'],  // eslint-disable-line
    setup() {
  
    }
  }
  </script>
  
  <style>
  
  </style>