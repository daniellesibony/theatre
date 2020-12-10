<template>
  <section v-if="ifShow" class="seat-preview">
    <div class="seat-card"></div>
    <span>{{ coords }}</span>

    <div v-if="isReserved"></div>
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
      isAvailble: false,
      isReserved: false,
      isSelected: false,
    
    };
  },

  methods: {
    // toggleReserve(){
    //   this.isReserved === !this.isReserved
    // },
    isReserved(){
      return this.isReserved === true
    }
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