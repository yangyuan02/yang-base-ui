<template>
  <div>
    <label>{{text}}</label>
    <input type="checkbox">
  </div>
</template>
<script>
export default {
  props: {
    text: {
      // checkbox显示的文本
      type: String,
      default: ''
    },
    defaultChecked: {
      // 是否默认选中
      type: Boolean,
      default: false
    },
    checked: {
      // 选中
      type: Boolean,
      default: false
    },
    onClick: {
      // onClick(checked, value)
    },
    value: {}, // 在回调中作为第二个参数返回
    size: {
      // 大小
      type: Number,
      default: 16
    },
    disabled: {
      // 是否禁用
      type: Boolean,
      default: false
    }
  }
};
</script>
<style lang="less" scoped>
</style>

