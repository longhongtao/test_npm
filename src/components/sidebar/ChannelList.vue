<template>
  <div>
    <div
      class="channelList"
      :style="{
        height: `${height}px`,
      }"
    >
      <div
        v-for="item in channelList"
        :key="item.id"
        class="item"
        :style="`width:${100 / columns}%`"
      >
        <ChannelS
          :data="item"
          :isActive="item.id === activeId"
          @active="$emit('active', item.id)"
        >
        </ChannelS>
      </div>
    </div>
    <div class="FlodDevd" @click="FlodDevd = !FlodDevd">
      {{ FlodDevd ? "折叠" : "展开" }}
    </div>
    
  </div>
</template>

<script>
import ChannelS from "./ChannelS.vue";
export default {
  components: {
    ChannelS,
  },
  props: {
    activeId: {
      type: Number,
      require: true,
    },
    channelList: [],
    columns: {
      type: Number,
      default: 2,
    },
  },
  data() {
    return {
      FlodDevd: true,
    };
  },
  computed: {
    height() {
      var rows = 3;
      if (this.FlodDevd) {
        //计算高度
        rows = Math.ceil(this.channelList.length / this.columns);
      }
      return rows * 38;
    },
  },
};
</script>

<style>
.FlodDevd {
  height: 30px;
  line-height: 30px;
  text-align: center;
  font-size: 14px;
  color: #ccc;
  cursor: pointer;
  clear: both;
  border-bottom: 1px solid #ccc;
}
.channelList {
  overflow: hidden;
  transition: 0.4s;
}
.item {
  float: left;
}
</style>