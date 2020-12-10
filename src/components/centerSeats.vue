<template>
  <section class="center-seats">
<div class="seat-row flex"  v-for="(row, i) in seats" :key="i">
<span v-for="(seat,j) in row" :key="j" >
  <!-- <seat-preview :x=seat.x :y=seat.y /> -->
  <seat-preview  :coords= {x:seat.x,y:seat.y} />
<!-- row ={{seat.x}}
col ={{seat.y}} -->
</span>

</div>
  </section>
</template>

<script>
import seatPreview from "../../src/components/seatPreview";
import SeatPreview from './seatPreview.vue';
export default {
data(){
    return {
       seats:[]
    }
},
created() {
  let seats=[]
  for(var i=0; i<6; i++) {
    seats[i] = [];
    for(var j=0; j<12; j++) {
        seats[i][j] = {
          x:i,
          y:j
        };
        this.seats = seats
    }
}
},
components:{
  seatPreview,
}
}
</script>

<style>

</style>