<template>
  <section class="seat-preview">
<div class="seat-card">


</div>



  </section>
</template>

<script>
import seatListVue from "./seatList.vue";
export default {
  props:{
    coords: Object
  },
  data() {
    return {
      availble: '',
      reserved: '',
      selected: '',
    };
  },
};
</script>

<style>
</style>