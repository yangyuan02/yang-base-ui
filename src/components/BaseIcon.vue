<template>
  <i class="icon" :class="'icon-' + type" :style="{'color': color, 'fontSize': size + 'px'}"></i>
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
    }
  }
};
</script>
<style lang="less" scoped>
</style>


