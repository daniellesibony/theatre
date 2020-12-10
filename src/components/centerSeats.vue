<template>
  <section class="center-seats">
<div  v-for="(seat, index) in seats" :key="index">
<span>X:{{seat[index].x}} y:{{seat[index].y}}</span>
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
  for(var i=0; i<9; i++) {
    seats[i] = [];
    for(var j=0; j<9; j++) {
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