<template>
  <div class="ui-radio" :class="className">
    <label>
      <span><input type="radio" :disabled="disabled" :checked="isChecked" @click="handleClick"></span>
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
.ui-radio {
  display: inline-block;
  label {
    display: flex;
    align-items: center;
    input {
      &[type='radio'] {
        position: relative;
        margin-top: 5px;
        margin-right: 4px;
        vertical-align: -4px;
        border: none;
        background-color: transparent;
        -webkit-appearance: none;
        -moz-appearance: none;
        -ms-appearance: none;
        -webkit-appearance: none;
        appearance: none;
        cursor: pointer;
      }

      &[type='radio']:focus {
        outline: none;
      }

      &[type='radio']:before,
      &[type='radio']:after {
        content: '';
        display: block;
        width: 18px;
        height: 18px;
        margin-top: -3px;
        border-radius: 50%;
        -webkit-transition: 240ms;
        -o-transition: 240ms;
        -ms-transition: 240ms;
        -moz-transition: 240ms;
        transition: 240ms;
      }

      &[type='radio']:before {
        position: absolute;
        left: 0;
        top: 0;
        background-color: #2196f3 !important;
        -webkit-transform: scale(0);
        -ms-transform: scale(0);
        -o-transform: scale(0);
        -moz-transform: scale(0);
        transform: scale(0);
      }

      &[type='radio']:checked:before {
        -webkit-transform: scale(0.7);
        -ms-transform: scale(0.7);
        -o-transform: scale(0.7);
        -moz-transform: scale(0.7);
        transform: scale(0.7);
      }

      &[type='radio']:disabled:checked:before {
        background-color: #bbbbbb !important;
      }

      &[type='radio']:checked:after {
        border-color: #2196f3 !important;
      }

      &[type='radio']:disabled:after,
      &[type='radio']:disabled:checked:after {
        border-color: #bbbbbb !important;
      }
    }
  }
}
</style>
