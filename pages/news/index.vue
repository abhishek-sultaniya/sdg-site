<template>
  <div class="home">
    <site-hero title="Events" subtitle="" image="" />
    <div v-if="events.length">
      <EventList :events="events" />
    </div>
    <div v-else>Loading</div>
  </div>
</template>

<script>
import { defineComponent, ref } from '@nuxtjs/composition-api';

import { collection, getDocs } from 'firebase/firestore';
import { projectFirestore } from '../../firebase/config';

import EventList from '../../components/news/EventList.vue';

export default defineComponent({
  components: { EventList },
  setup() {
    const events = ref([]);
    const res = collection(projectFirestore, 'posts');
    getDocs(res).then((snapshot) => {
      const docs = [];
      snapshot.docs.forEach((doc) => {
        docs.push({ ...doc.data(), id: doc.id });
      });
      events.value = docs;
    });
    return { events };
  },
});
</script>
