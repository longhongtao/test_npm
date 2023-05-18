<template>
  <div class="color">
    <div class="test">
      <round />
    </div>
  </div>
</template>

<script>
import round from "./round.vue";
export default {
  components: {
    round,
  },
};
</script>

<style scoped lang="scss">
.color {
  width: 40%;
  height: 100%;
  background-color: #3f9eff;
  border-radius: 20px;
  position: relative;
}
.test {
  width: 45px;
  height: 45px;
  display: inline-block;
  vertical-align: middle;
  right: 0;
  top: -5px;
  margin-left: 85%;
}
</style>