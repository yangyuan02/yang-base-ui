<template>
  <i class="ui-icon iconfont" :class="['icon-' + type, className]" :style="{'color': color, 'fontSize': size + 'px'}"></i>
</template>
<script>
export default {
  props: {
    type: {
      type: String,
      required: true
    },
    size: {
      type: Number,
      default: 14
    },
    color: {
      type: String,
      default: '#000000'
    },
    className: {
      type: String,
      default: ''
    }
  }
};
</script>
<style lang="less" scoped>
</style>


