<template>
  <div class="back">
    <color></color>
  </div>
</template>

<script>
import color from "./color.vue";
export default {
  components: {
    color,
  },
};
</script>

<style scoped lang="scss">
.back {
  width: 100%;
  height: 100%;
  background-color: #ccc;
  border-radius: 20px;
}
</style>