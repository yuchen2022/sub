<template>
  <div class="flex">
    <SubscribeBox :boxNumber="1" :subs="subs.subscription_1" />
    <!-- <SubscribeBox :boxNumber="2" :subs="subs.subscription_2" />
    <SubscribeBox :boxNumber="3" :subs="subs.subscription_3" /> -->
  </div>
</template>
<script>
import SubscribeBox from "./SubscribeBox.vue";

export default {
  data() {
    return {
      subs: {
        subscription_1: [
          {
            id: 1,
            price: 100,
            duration: 86400,
            off: 0,
            is_selected: false,
          },
          {
            id: 2,
            price: 200,
            duration: 2592000,
            off: 10,
            is_selected: false,
          },
          {
            id: 3,
            price: 300,
            duration: 31536000,
            off: 0,
            is_selected: true,
          },
        ],
        subscription_2: [
          {
            id: 4,
            price: 400,
            duration: 86400,
            off: 0,
            is_selected: false,
          },
          {
            id: 5,
            price: 500,
            duration: 2592000,
            off: 0,
            is_selected: false,
          },
          {
            id: 6,
            price: 600,
            duration: 31536000,
            off: 10,
            is_selected: false,
          },
        ],
        subscription_3: [
          {
            id: 7,
            price: 700,
            duration: 86400,
            off: 0,
            is_selected: false,
          },
          {
            id: 8,
            price: 800,
            duration: 2592000,
            off: 0,
            is_selected: false,
          },
          {
            id: 9,
            price: 900,
            duration: 31536000,
            off: 10,
            is_selected: false,
          },
        ],
      },
    };
  },
  components: { SubscribeBox },
};
</script>
