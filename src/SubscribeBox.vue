<template>
  <div
    class="shadow-md rounded-md p-10 pt-2 mt-10 h-96 flex flex-col max-w-fit mx-auto justify-center"
  >
    <HeaderBadge :newSubs="newSubs" />

    <div class="flex">
      <SubBtn :newSubs="newSubs" v-for="subDuration in subs" />
    </div>

    <OffHandler :newSubs="newSubs" />
  </div>
</template>
<script>
import SubBtn from "./Sub-btn.vue";
import HeaderBadge from "./HeaderBadge.vue";
import OffHandler from "./components/Off-handler.vue";

export default {
  props: ["boxNumber", "subs"],
  components: {
    SubBtn,
    HeaderBadge,
    OffHandler,
  },
  data() {
    return {
      i: 3,
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
    changeID() {
      return this.subHandler.id;
    },
  },
};
</script>
