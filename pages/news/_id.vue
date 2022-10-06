<template>
  <h1>{{ eventID }}</h1>
</template>

<script>
import { defineComponent } from '@nuxtjs/composition-api';

export default defineComponent({
  setup(params) {
    const eventID = params.id;
    return { eventID };
  },
});
</script>
