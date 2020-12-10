<template>
  <!-- <section v-if=" ifShow" class="seat-preview"> -->
  <section  class="seat-preview">
<div class="seat-card"></div>
<img v-if="!isBlank" class="seat-svg" src="../../src/assets/svgs/sofa.svg" alt="">
<div class="blank" v-if="isBlank">---</div>

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
    // ifShow(){
    //   if ((this.coords.x<2)&& (this.coords.y<5 || this.coords.y > 23 )) return false;
    //   if ((this.coords.x<4&&this.coords.x>1)&& (this.coords.y<4 || this.coords.y > 24 )) return false;
    //   if ((this.coords.x<5&&this.coords.x>3)&& (this.coords.y<3 || this.coords.y > 26 )) return false;
    //   if ((this.coords.x<7&&this.coords.x>4)&& (this.coords.y<1 )) return false;
    //   // if ((this.coords.x>7)&& (this.coords.y<19&&this.coords.y>9 )) return false;
     
    //   // if (this.coords.x===8|| this.coords.x===20) return false;
    //   else return true
    // },
    isBlank(){
      // if ((this.coords.x<2)&& (this.coords.y<5 || this.coords.y > 23 )) return false;
          if ((this.coords.x<2)&& (this.coords.y<5 || this.coords.y > 23 )) return true;
      if ((this.coords.x<4&&this.coords.x>1)&& (this.coords.y<4 || this.coords.y > 24 )) return true;
      if ((this.coords.x<5&&this.coords.x>3)&& (this.coords.y<3 || this.coords.y > 26 )) return true;
      if ((this.coords.x<7&&this.coords.x>4)&& (this.coords.y<1 )) return true;
      if ((this.coords.x>5)&& (this.coords.y<20&&this.coords.y>7 )) return true;
      if ((this.coords.x===7)&& (this.coords.y<20 &&this.coords.y>5 )) return true;
      if ((this.coords.x>7)&& (this.coords.y<20)) return true;
      if (this.coords.y===8|| this.coords.y===20) return true;
      else return false
    }
  }
};
</script>

<style>
</style>