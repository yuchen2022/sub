<template>
  
  <div class="shadow-md rounded-md p-10 pt-2 mt-10 h-96 flex flex-col  justify-center">
   
    
    <div class="bg-purple-950 mb-4 text-white p-3 rounded-md">
      subscription {{ boxNumber }}
      
    </div>
    <div class="flex" >
      <SubBtn :newSubs="newSubs" @click="i=1" />
      <SubBtn :newSubs="newSubs" @click="i=2"/>
      <SubBtn :newSubs="newSubs" @click="i=3"/>
      
     
    </div>
    
  
   <OffHandler :newSubs="newSubs" />
  </div>
</template>
<script>
import SubBtn from "./Sub-btn.vue";

import OffHandler from "./components/Off-handler.vue";

export default {
  props: ["boxNumber", "subs"],
  components: {
    SubBtn,
  
    OffHandler
},
  data() {
    return {
     
     
      i: 1,
      newSubs: null,
    };
  },
  created() {
    this.newSubs = this.subs.reduce((subs, objSubs) => {
      subs[objSubs.id] = objSubs;

      return subs;
    }, {});
  },
  
  computed: {
    subHandler() {
      let data = this.newSubs[this.i];

      return data;
    },
    changeID(){
  
      return this.subHandler.id;

    }
  },
};
</script>
