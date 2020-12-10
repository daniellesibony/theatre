<template>
  <section v-if="ifShow" class="seat-preview">
    <div class="seat-card"></div>
    <img
      src="../../src/assets/svgs/sofa.svg"
      alt=""
      @click="open"
      :class="{ reserved: isReserved, selected: isSelected }"
    />
    <!-- <el-button v-if="isReserved" type="text"></el-button> -->
    <div  v-if="isShown" id="myModal" class="modal">
      <div class="modal-content">
        <span  @click="cancel" class="close">&times;</span>
        <p>Confirm This Seat</p>
        <button @click="confirm">Confirm</button>
        <button @click="cancel">Cancel</button>
      </div>
    </div>
  </section>
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
      // setTimeout(this.isShown = true, 500)

      this.isShown = true

      setTimeout(this.cancel, 10000)
    },
    cancel(){
      this.isShown = false
      this.isReserved = false

    },

    confirm(){
       this.isShown = false

      this.isSelected = true
    }
  },
  computed: {
    ifShow() {
      if (this.coords.x === 0 && (this.coords.y === 0 || this.coords.y === 11))
        return false;
      else return true;
    },
  },
};
</script>

<style>
</style>