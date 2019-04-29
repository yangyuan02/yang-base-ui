<template>
  <div class="ui-input-container">
    <span class="input-box-name">{{text}}</span>
    <input type="text" ref="input" :value="value" @input="$emit('input', $event.target.value)" v-bind="$attrs">
  </div>
</template>
<script>
export default {
  inheritAttrs: false,
  props: {
    text: {
      // 表单名称
      type: String,
      default: ''
    },
    value: {
      // input值
      type: String,
      default: ''
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
.ui-input-container {
  input {
    border: 1px solid #eee;
  }
}
</style>

