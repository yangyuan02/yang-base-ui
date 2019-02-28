<template>
  <div class="ui-switch-container" :class="className">
    <input type="checkbox" class="switch" :disabled="disabled" :checked="isChecked" @click="handleClick" />
    <span for="switch"></span>
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
@switchHeight: 30px;
@switchWidth: 60px; /*改变大小只需要改变这个两个的值，后面会用到这两个值*/
.ui-switch-container {
  height: @switchHeight;
  width: @switchWidth;
  margin-bottom: 5px;
  display: inline-block;
  .switch {
    display: none;
    &:checked ~ span:after {
      opacity: 1;
    }

    &:checked ~ span:before {
      opacity: 0;
    }

    &:checked ~ span {
      background-color: red;
    }
    &:disabled ~ span {
      // background-color: #bbb;
      cursor: not-allowed;
    }
  }

  span {
    display: block;
    background-color: #eeeeee;
    height: 100%;
    width: 100%;
    cursor: pointer;
    border-radius: 25px;
    &:before {
      content: '';
      display: block;
      border-radius: 25px;
      height: 100%;
      width: @switchHeight;
      background-color: white;
      opacity: 1;
      box-shadow: 1px 1px 1px 1px rgba(0, 0, 0, 0.08);
      -ms-transition: all 0.2s ease; /* IE 9 */
      -moz-transition: all 0.2s ease; /* Firefox */
      -webkit-transition: all 0.2s ease; /* Safari and Chrome */
      -o-transition: all 0.2s ease; /* Opera */
    }
    &:after {
      position: relative;
      top: -@switchHeight;
      left: @switchHeight;
      content: '';
      display: block;
      border-radius: 25px;
      height: 100%;
      width: @switchHeight;
      background-color: white;
      opacity: 0;
      box-shadow: 1px 1px 1px 1px rgba(0, 0, 0, 0.08);
      -ms-transition: all 0.2s ease; /* IE 9 */
      -moz-transition: all 0.2s ease; /* Firefox */
      -webkit-transition: all 0.2s ease; /* Safari and Chrome */
      -o-transition: all 0.2s ease; /* Opera */
    }
  }
}
</style>


