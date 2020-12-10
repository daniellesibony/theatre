<template>
  <section class="seat-preview">




  </section>
</template>

<script>
import seatListVue from "./seatList.vue";
export default {
  props:{
    seat: Object
  },
  data() {
    return {
      // seats: [{ available: "" }, { reserved: "" }, { selected: "" }],
      availble: '',
      reserved: '',
      selected: '',
    };
  },
};
</script>

<style>
</style>