<template>
  <div class="channel">
    <Item :isActive="isActive" @active="$emit('active')">
      <div class="liner">
        <span class="name">{{ data.name }}</span>
        <span class="number">{{ data.channel }}</span>
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
    data: {
      type: Object,
      default: () => ({}),
    },
  },
  components: {
    Item,
  },
};
</script>
  
  <style scoped>
.channel {
  width: 100%;
  height: 38px;
  line-height: 38px;
}
.liner {
  width: 100%;
  padding: 0 20px;
}
.name {
  font-size: 18px;
}
.number {
  font-size: 12px;
  margin-left: 8px;
  color: #999;
}
.name,
.number {
  float: left;
}
</style>