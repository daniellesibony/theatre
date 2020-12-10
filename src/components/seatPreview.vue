<template>
  <section v-if=" ifShow" class="seat-preview">
<div class="seat-card"></div>
<img src="../../src/assets/svgs/sofa.svg" alt="">


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
  computed:{
    ifShow(){
      if (this.coords.x===0 && (this.coords.y===0 || this.coords.y===11 )) return false;
      else return true
    }
  }
};
</script>

<style>
</style>