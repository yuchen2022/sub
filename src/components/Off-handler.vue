<template>

    
     <div class="text-purple-900 m-2 p-2 rounded-md shadow-md shadow-purple-200">
      <div class="relative font-semibold my-1">
        price : {{ newSubs[i].price }}
      </div>
      <span :class="{'hidden': newSubs[i].off == 0}" class="absolute top-3 left-16"
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
      <div :class="{'hidden': newSubs[i].off == 0}" class="font-bold my-1 text-purple-900">
        off price :
        <span>{{ this.offPrice }}</span>
        <span>{{ checking }}</span>
      </div>

      
    </div>
</template>
<script>
export default {
  props:["newSubs"],
  data() {
  
    return {
      i: 2,
      offPrice:10
    };

  },
computed:{
    checking()
    {
        console.log("checking",this.newSubs[this.i])
    }
}
 
};
</script>

