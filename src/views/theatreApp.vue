<template>
  <section class="theatre-app">
  <h1 class="screen">Screen is this Way</h1>
<div class="flex">
  <left-side-seats/>
<center-seats/>
</div>




  </section>
</template>

<script>
import centerSeats from "../../src/components/centerSeats";
import leftSideSeats from '../components/leftSideSeats';
export default {
  components: {
    centerSeats,
    leftSideSeats,
  },
}
</script>

<style>

</style>
