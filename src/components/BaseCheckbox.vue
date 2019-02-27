<template>
  <div class="ui-checkbox" :class="className">
    <label>
      <span><input type="checkbox" :disabled="disabled" :checked="isChecked" @click="handleClick"></span>
      <span>{{text}}</span>
    </label>
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
    },
    className: {
      // 外部class类
      type: String,
      default: ''
    }
  },
  methods: {
    handleClick(e) {
      this.$emit('onClick', e, this.value);
    }
  },
  computed: {
    isChecked: function() {
      return this.checked || this.defaultChecked;
    }
  }
};
</script>
<style lang="less" scoped>
.ui-checkbox {
  display: inline-block;
  label {
    display: flex;
    align-items: center;
  }
}
</style>
