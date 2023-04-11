<template>
  <button
    class="bg-fuchsia-200 rounded-lg whitespace-nowrap text-purple-800 shadow-md shadow-purple-500 px-2 font-semibold p-2 m-3"
  >
    duration :
    {{ durTime }} days
  </button>

</template>
<script>
export default {
  props:["newSubs"],
  data() {
  
    return {
      i: 2,
      // newSubs: null,
    };

  },
 computed:{
  durTime(){

     let durTime = this.newSubs[this.i].duration
     return durTime/3600/24;
     
  }
 }
 
};
</script>
