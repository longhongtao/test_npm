<template>
  <div
    id="button-global"
    :style="{
      width: `${width}px`,
      height: `${height}px`,
    }"
  >
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: {
    width: {
      type: Number,
      default: 500,
    },
    height: {
      type: Number,
      default: 50,
    },
  },
  mounted() {
    // const home = document.querySelector("#button-global");
    // const childCount = home.querySelectorAll("button").length;
    // console.log(childCount);
  },
};
</script>

<style scoped lang="scss">
#button-global {
  display: flex;
  flex-wrap: nowrap;
  border-radius: 4px;
  overflow: hidden;
}
#button-global::v-deep * {
  padding: 0;
  border-radius: 0 !important; /* 穿透组件边界，将样式应用到组件外部 */
}
#button-global :not(:last-child)::v-deep *{
    border-right-color: hsla(0,0%,100%,.5);
}
</style>