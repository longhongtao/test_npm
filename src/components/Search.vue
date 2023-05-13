<template>
  <form @submit.prevent="handSearch" class="search">
    <input type="text" :placeholder="placeholder" v-model="inputValue" />
  </form>
</template>

<script>
export default {
  methods: {
    handSearch() {
      if (this.inputValue != "") {
        this.$emit("search", this.inputValue);
      }
    },
  },
  props: {
    placeholder: {
      type: String,
      default: "搜索关键字",
    },
  },
  data() {
    return {
      inputValue: "",
    };
  },
};
</script>

<style scoped>
.search {
  width: 100%;
  height: 100%;
  box-sizing: border-box;
  border-radius: 3px;
  border: 1px solid #cecece;
}
.search input {
  border: none;
  outline: none;
  width: 100%;
  height: 100%;
  padding-left: 10px;
  padding-right: 10px;
  box-sizing: border-box;
}
</style>