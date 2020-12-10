<template>
  <section  class="seat-preview">
<div class="seat-card"></div>
<img v-if="!isBlank" class="seat-svg" src="../../src/assets/svgs/sofa.svg" alt=""  @click="open"
      :class="{ selected: isSelected, reserved: isReserved }">
<div class="blank" v-if="isBlank">---</div>
 <div  v-if="isShown" id="myModal" class="modal">
      <div class="modal-content">
        <span  @click="cancel" class="close">&times;</span>
        <p>Confirm This Seat</p>
        <button @click="confirm">Confirm</button>
        <button @click="cancel">Cancel</button>
      </div>
    </div>
    

  </section>
  <!-- </div> -->
</template>

<script>
import seatListVue from "./seatList.vue";
export default {
  props: {
    coords: Object,
  },
  data() {
    return {
      isAvailble: false,
      isReserved: false,
      isSelected: false,
      isShown: false
    };
  },

  methods: {
    open(){
      this.isReserved = true
      this.isShown = true
      setTimeout(this.cancel, 10000)
    },
    cancel(){
      this.isShown = false
      this.isReserved = false
    },
    confirm(){
      (this.isSelected = true) && (this.isReserved = false)
      this.isShown = false
      // this.isSelected = true
     
    },
  },
  computed:{
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