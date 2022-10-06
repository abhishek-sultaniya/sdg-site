<template>
  <div class="home">
    <h1>News/events</h1>
    <!-- <div v-if="events.length"> -->
    <!-- <EventList :events="events" /> -->
    <!-- </div> -->
    <!-- <div v-else> -->
    Loading
    <!-- </div> -->
  </div>
</template>
  
  <script>
  import {ref} from 'vue' // eslint-disable-line
  
  // import { collection, query,getDocs, snapshotEqual } from "firebase/firestore";
  import { collection,getDocs} from "firebase/firestore"; 
  import EventList from '../../components/newss/EventList.vue'
  
  import {projectFirestore} from '../../firebase/config'
  
  export default {
      components:{EventList}, // eslint-disable-line
      setup() {
        const events = ref([])     
        const res=collection(projectFirestore,'posts')
        console.log(res) // eslint-disable-line
        getDocs(res).then(snapshot =>{
          const docs=[]
          snapshot.docs.forEach(doc =>{
            docs.push({...doc.data(),id:doc.id})
          })
          events.value = docs
        })
        return { events};       
      },
  }
  
  </script>
  