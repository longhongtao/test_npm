<template>
  <div>
    <Asdie
      :channelList="channelList"
      :placeholder="'搜索'"
      :title="'发现频道'"
      :icon="'>'"
      @search="search"
    />
  </div>
</template>
<script>
import Asdie from "./components/Asdie.vue";
import axios from "axios";
export default {
  components: {
    Asdie,
  },
  data() {
    return {
      channelList: [],
    };
  },
  created() {
    axios({
      url: "http://localhost:8085/test/all",
    }).then((ref) => {
      var data = ref.data;
      //数据过滤
      this.channelList = data.filter((item) => item.id != 1);
    });
  },
  methods: {
    search(e) {
      window.alert(e);
    },
  },
};
</script>

<style scoped>
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