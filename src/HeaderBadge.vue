<template>
  <div class="flex justify-between mb-3">
    <div
      :class="{ hidden: newSubs[i].off == 0 }"
      class="bg-purple-200 p-2 rounded-md w-1/3 text-center text-lg shadow-md shadow-purple-400 font-extrabold text-purple-900"
    >
      off : {{ newSubs[i].off }} %
    </div>
    <div
      :class="{ hidden: newSubs[i].is_selected == false }"
      class="bg-purple-200 p-2 rounded-md w-1/3 tracking-wider text-center text-lg shadow-md shadow-purple-400 font-extrabold text-purple-900"
    >
      special offer!
    </div>
  </div>
  <div class="bg-purple-950 mb-4 text-white p-3 rounded-md">
    subscription {{ i }}
  </div>
</template>
<script>
export default {
  props: ["boxNumber", "newSubs"],
  data() {
    return {
      i: 3,
    };
  },
};
</script>
