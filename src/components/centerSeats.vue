<template>
  <section class="center-seats">
<div  v-for="(row, i) in seats" :key="i">
<span v-for="(seat,j) in row" :key="j" >
row ={{seat.x}}
col ={{seat.y}}
</span>

</div>
  </section>
</template>

<script>
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
}
</script>

<style>

</style>