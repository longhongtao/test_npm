<template>
  <div class="home">
    <div class="search">
      <Search @search="search" :placeholder="placeholder" />
    </div>
    <TitleMenu :isActive="activeId === 1" @active="activeId = 1">
      <template v-slot:title>{{ title }}</template>
      <template v-slot:icon>{{ icon }}</template>
    </TitleMenu>
    <ChannelList
      :activeId="activeId"
      @active="activeId = $event"
      :channelList="channelList"
      :columns="columns"
    >
    </ChannelList>
  </div>
</template>
  
  <script>
import TitleMenu from "./TitleMenu.vue";
import ChannelList from "./ChannelList.vue";
import Search from "./Search.vue";
export default {
  components: {
    TitleMenu,
    ChannelList,
    Search,
  },
  methods: {
    search(e) {
      this.$emit("search", e);
    },
  },
  data() {
    return {
      activeId: 1,
    };
  },
  props: {
    placeholder: {
      type: String,
    },
    title: {
      type: String,
    },
    icon: {
      type: String,
    },
    channelList: [],
    columns: {
      type: Number,
      default: 2,
    },
  },
};
</script>
  
  <style scoped>
.home {
  width: 100%;
  height: 100%;
  overflow: auto;
}
.search {
  width: 100%;
  height: 35px;
  margin-top: 10px;
  margin-bottom: 10px;
  padding-left: 10px;
  padding-right: 10px;
  box-sizing: border-box;
}
</style>