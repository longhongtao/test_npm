<template>
  <div class="item">
    <button
      :class="typeS === active ? typeS : 'default'"
      @click="$emit('click')"
      :disabled="disabled"
      :style="{
        width: `${width}`,
        height: `${height}`,
        borderRadius: `${radius}px`,
      }"
      round
      plain
    >
      <slot></slot>
      <div class="loa">
        <Loading :loading="loading"></Loading>
      </div>
    </button>
  </div>
</template>

<script>
import Loading from "../loading/loading.vue";
export default {
  components: {
    Loading,
  },
  props: {
    loading: {
      type: Boolean,
      default: false,
    },
    type: {
      type: String,
      default: "default",
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    height: {
      type: String,
      default: "100%",
    },
    width: {
      type: String,
      default: "100%",
    },
    round: {
      type: Boolean,
      default: false,
    },
    plain: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      ButType: [
        "primary",
        "success",
        "info",
        "warning",
        "danger",
        "default",
        "default-plain",
        "primary-plain",
        "success-plain",
        "info-plain",
        "warning-plain",
        "danger-plain",
      ],
      active: "",
      radius: {
        type: Number,
        default: 3,
      },
      typeS: this.type,
    };
  },
  mounted() {
    this.plain ? (this.typeS = `${this.typeS}-plain`) : this.typeS;
    this.active = this.ButType.find((item) => item === this.typeS);
    this.radius = this.round ? 20 : 4;
  },
  computed: {},
  methods: {},
};
</script>

<style scoped lang="scss">
@import "../style/button.scss";
button:disabled {
  cursor: not-allowed;
}
button {
  height: 100%;
  width: 100%;
  border: 1px solid;
}
.loa {
  display: flex;
  align-items: center;
  justify-content: center;
}
.item {
  position: relative;
  padding: 0 10px;
  width: 100%;
  height: 100%;
  overflow: hidden;
}
.default {
  @include hover($color: #409eff, $background: #ecf5ff, $border: none);
  @include color(#606266, none, #dcdfe6);
  @include disabled($background: #fff, $color: #c0c4cc, $border: #ebeef5);
  @include active($background: #ecf5ff, $color: #3a8ee6, $border: #3a8ee6);
}
.default-plain {
  @include hover($background: #fff, $color: #409eff, $border: #409eff);
  @include disabled($background: #fff, $color: #c0c4cc, $border: #ebeef5);
  @include color($background: #fff, $color: #606266, $border: #dcdfe6);
  @include active($background: #ecf5ff, $color: #3a8ee6, $border: #3a8ee6);
}
.primary {
  @include color($background: #409eff);
  @include hover($background: #66b1ff);
  @include disabled($background: #a0cfff);
  @include active($background: #3a8ee6);
}
.primary-plain {
  @include color(#409eff, #ecf5ff, #b3d8ff);
  @include hover($background: #3a8ee6);
  @include active($background: #3a8ee6);
  @include disabled($background: #ecf5ff, $color: #8cc5ff);
}

.success {
  @include color($background: #67c23a);
  @include hover($background: #85ce61);
  @include disabled($background: #b2e19d);
  @include active($background: #5daf34);
}
.success-plain {
  @include color(#67c23a, #f0f9eb, #c2e7b0);
  @include hover($background: #67c23a);
  @include disabled($background: #f0f9eb, $color: #a4da89);
  @include active($background: #5daf34);
}

.info {
  @include hover($background: #a6a9ad);
  @include color($background: #909399);
  @include disabled($background: #c8c9cc);
  @include active($background: #82848a);
}
.info-plain {
  @include hover($background: #909399);
  @include color(#909399, #f4f4f5, #d3d4d6);
  @include disabled($background: #f4f4f5, $color: #bcbec2);
  @include active($background: #82848a);
}
.warning {
  @include color($background: #e6a23c);
  @include hover($background: #ebb563);
  @include disabled($background: #f2d19e);
  @include active($background: #cf9236);
}
.warning-plain {
  @include color(#e6a23c, #fdf6ec, #f5dab1);
  @include hover($background: #e6a23c);
  @include disabled($background: #fdf6ec, $color: #f0c78a);
  @include active($background: #cf9236);
}
.danger {
  @include color($background: #f56c6c);
  @include hover($background: #f78989);
  @include disabled($background: #fab6b5);
  @include active($background: #dd6161);
}
.danger-plain {
  @include color(#f56c6c, #fef0f0, #fbc4c4);
  @include hover($background: #f56c6c);
  @include disabled($background: #ffeff0, $color: #f9a7a7);
  @include active($background: #dd6161);
}
</style>