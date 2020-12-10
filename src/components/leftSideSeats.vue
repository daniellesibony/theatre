<template>
  <section class="left-seats">
<div class="seat-row flex"  v-for="(row, i) in seats" :key="i">
<span v-for="(seat,j) in row" :key="j" >
  <seat-preview  :coords= {x:seat.x,y:seat.y} />
</span>

</div>
  </section>
</template>

<script>
import seatPreview from "../../src/components/seatPreview";

export default {
data(){
    return {
       seats:[]
    }
},
created() {
  let seats=[]
  for(var i=0; i<8; i++) {
    seats[i] = [];
    for(var j=0; j<7; j++) {
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