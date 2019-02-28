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
    input {
      &[type='checkbox'] {
        position: relative;
        /*vertical-align: -4px;*/
        border: none;
        -webkit-appearance: none;
        -ms-appearance: none;
        -moz-appearance: none;
        -o-appearance: none;
        appearance: none;
        cursor: pointer;
      }

      &[type='checkbox']:focus {
        outline: none;
      }

      &[type='checkbox']:after {
        content: '';
        display: block;
        width: 18px;
        height: 18px;
        margin-top: -2px;
        margin-right: 5px;
        border-radius: 2px;
        -webkit-transition: 240ms;
        -o-transition: 240ms;
        -ms-transform: 240ms;
        -moz-transform: 240ms;
        transition: 240ms;
        background: white;
      }

      &[type='checkbox']:checked:before {
        content: '';
        position: absolute;
        top: 0;
        left: 6px;
        width: 6px;
        height: 12px;
        border: 2px solid #fff;
        border-top-width: 0;
        border-left-width: 0;
        -webkit-transform: rotate(45deg);
        -ms-transform: rotate(45deg);
        -o-transform: rotate(45deg);
        -moz-transform: rotate(45deg);
        transform: rotate(45deg);
      }

      &[type='checkbox']:checked:after {
        background-color: #2196f3 !important;
        border-color: #2196f3 !important;
      }

      &[type='checkbox']:disabled {
        cursor: not-allowed;
      }

      &[type='checkbox']:disabled:after {
        border-color: #bbbbbb !important;
      }

      &[type='checkbox']:disabled:checked:after {
        background-color: #bbbbbb !important;
        border-color: transparent !important;
      }
    }
  }
}
</style>
