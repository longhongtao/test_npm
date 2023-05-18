<template>
  <div class="home">
    <div class="pop">
      <pop></pop>  
    </div>
  </div>
</template>

<script>
import pop from "./components/pop-up/surface.vue";
import round from './components/pop-up/round.vue'
export default {
  components: {
    pop,
    round
  },
};
</script>

<style scoped>
.pop{
  width: 600px;
  height: 40px;
}
.test{
  width: 25px;
  height: 25px;
}
</style>