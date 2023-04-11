<template>
  
  <div class="shadow-md rounded-md p-10 pt-2 mt-10 ">
    <div :class="{'hidden': subHandler.off == 0}" class=" font-semibold pl-3 mb-2 shadow-md p-2 bg-purple-200 rounded-md">
        off : {{ subHandler.off }} %
      </div>
    
    <div class="bg-purple-950 mb-4 text-white p-3 rounded-md">
      subscription {{ boxNumber }}
      
    </div>
    <div class="flex" >
      <SubBtn :newSubs="newSubs" @click="i=1" />
      <SubBtn :newSubs="newSubs" @click="i=2"/>
      <SubBtn :newSubs="newSubs" @click="i=3"/>
      
     
    </div>
  
    <div class="text-purple-900 m-2 p-2 rounded-md shadow-md shadow-purple-200">
      <div class="relative font-semibold my-1">
        price : {{ subHandler.price }}
      </div>
      <span :class="{'hidden': subHandler.off == 0}" class="absolute top-3 left-16"
        ><svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="#FF0000"
          class="w-6 h-6"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M2.25 6L9 12.75l4.286-4.286a11.948 11.948 0 014.306 6.43l.776 2.898m0 0l3.182-5.511m-3.182 5.51l-5.511-3.181"
          />
        </svg>
      </span>
      <div :class="{'hidden': subHandler.off == 0}" class="font-bold my-1 text-purple-900">
        off price : {{ offPrice }}
      </div>

      
    </div>
  </div>
</template>
<script>
import SubBtn from "./Sub-btn.vue";
export default {
  props: ["boxNumber", "subs"],
  components: {
    SubBtn,
  },
  data() {
    return {
     
      offPrice: 10,
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
