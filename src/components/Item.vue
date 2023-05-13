<template>
  <div class="item" :class="{ active: isActive }" @click="disposeAtive">
    <!-- 使用插槽 -->
    <slot></slot>
  </div>
</template>
<script>
export default {
  props: {
    isActive: {
      type: Boolean, //传递的数据类型
    },
  },
  methods: {
    disposeAtive() {
      //抛出一个事件
      this.$emit("active");
    },
  },
};
</script>

<style scoped>
.active {
  background: #e7e7e7;
}
.item {
  cursor: pointer;
  width: 100%;
  height: 100%;
  transition: 0.3s;
}
.item:hover {
  background: #f4f4f4;
}
</style>