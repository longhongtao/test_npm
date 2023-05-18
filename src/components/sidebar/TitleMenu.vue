<template>
  <div class="menu">
    <Item :isActive="isActive" @active="$emit('active')">
      <div class="liner">
        <div class="left">
          <slot name="title"></slot>
        </div>
        <div class="right">
          <slot name="icon"></slot>
        </div>
      </div>
    </Item>
  </div>
</template>

<script>
import Item from "./Item.vue";
export default {
  props: {
    isActive: {
      type: Boolean, //传递的数据类型
    },
  },
  components: {
    Item,
  },
};
</script>

<style scoped>
.menu {
  width: 100%;
  height: 38px;
  line-height: 38px;
}
.liner {
  padding: 0 20px;
}
.left {
  font-size: 18px;
  float: left;
}
.right {
  font-size: 12px;
  float: right;
}
</style>