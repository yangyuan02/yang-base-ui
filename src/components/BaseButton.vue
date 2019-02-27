<template>
  <button class="ui-button" :class="className" :disabled="disabled" :type="type" @click="handleClick">
    <base-icon v-if="icon && !isLoading" :type="icon" :size="16" className="mRight10"></base-icon>
    <base-icon v-if="isLoading" type="loading" :size="16" className="mRight10"></base-icon>
    <span>{{isLoading ? '加载中' : text}}</span>
  </button>
</template>

<script>
import BaseIcon from './BaseIcon';
export default {
  props: {
    text: {
      // 按钮文字
      type: String,
      default: ''
    },
    icon: {
      // 按钮图标类型
      type: String,
      default: ''
    },
    type: {
      // 按钮类型
      type: String,
      default: ''
    },
    disabled: {
      // 是否禁用
      type: Boolean,
      default: false
    },
    className: {
      // 外部class类
      type: String,
      default: ''
    },
    isLoading: {
      // 是否加载状态
      type: Boolean,
      default: false
    },
    onClick: {} // 点击按钮触发的回调
  },
  components: {
    BaseIcon
  },
  methods: {
    handleClick(e) {
      if (this.isLoading) {
        return false;
      }
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

