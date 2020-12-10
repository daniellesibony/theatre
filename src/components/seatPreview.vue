<template>
  <section class="seat-preview">
<div class="seat-card"></div>
<span>{{coords}}</span>


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