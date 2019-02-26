<template>
  <button class="ui-button" :class="className" :disabled="disabled" :type="type" @click="handleClick">
    <base-icon :type="icon" v-if="icon"></base-icon>
    <span>{{text}}</span>
  </button>
</template>

<script>
import BaseIcon from './BaseIcon';
export default {
  props: {
    text: {
      type: String,
      default: ''
    },
    icon: {
      type: String,
      default: ''
    },
    type: {
      type: String,
      default: ''
    },
    disabled: {
      type: Boolean,
      default: false
    },
    className: {
      type: String,
      default: ''
    },
    onClick: {}
  },
  components: {
    BaseIcon
  },
  methods: {
    handleClick(e) {
      this.$emit('onClick', e);
    }
  }
};
</script>

<style lang="less" scoped>
@disabled-color: #dadada;
.borde-background-color(@brColor, @bgColor, @color) {
  border-color: @brColor;
  background-color: @bgColor;
  color: @color;
}
.ui-button {
  padding: 12px 20px;
  font-size: 14px;
  line-height: 1;
  cursor: pointer;
  border-width: 1px;
  border-style: solid;
  .borde-background-color(#dcdfe6, #fff, #606266);
  &:disabled {
    cursor: not-allowed;
    color: @disabled-color;
  }
  &:loading {
    cursor: not-allowed;
    color: @disabled-color;
  }
  &[type='primary'] {
    .borde-background-color(#409eff, #409eff, #fff);
  }
  &[type='success'] {
    .borde-background-color(#67c23a, #67c23a, #fff);
  }
  &[type='warning'] {
    .borde-background-color(#e6a23c, #e6a23c, #fff);
  }
}
</style>

