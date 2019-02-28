<template>
  <div id="app">
    <div>
      <p style="margin-bottom:20px;">Button按钮</p>
      <base-button @onClick="handleClick" text="默认按钮" className="mRight10" icon="shezhi"></base-button>
      <base-button @onClick="handleClick" text="主要按钮" icon="shezhi" :isLoading="true" type="primary" className="mRight10"></base-button>
      <base-button @onClick="handleClick" text="成功按钮" :disabled="true" type="success" className="mRight10"></base-button>
      <base-button @onClick="handleClick" text="警告按钮" :disabled="true" type="warning" className="mRight10"></base-button>
    </div>
    <div style="margin-top:40px;">
      <p style="margin-bottom:20px;">Checkbox多选框</p>
      <base-checkbox text="电影" @onClick="handleCheckbox" :value="{text:'电影', id:1}" className="mRight10"></base-checkbox>
      <base-checkbox text="吃饭" @onClick="handleCheckbox" :value="{text:'吃饭', id:2}" :defaultChecked="true" :disabled="true" className="mRight10"></base-checkbox>
      <base-checkbox text="打游戏" @onClick="handleCheckbox" :value="{text:'打游戏', id:3}" :checked="true" :disabled="false" className="mRight10"></base-checkbox>
    </div>
    <div style="margin-top:40px;">
      <p style="margin-bottom:20px;">Radio单选框</p>
      <base-radio text="电影" @onClick="handleRadio" :value="{text:'电影', id:1}" className="mRight10"></base-radio>
      <base-radio text="吃饭" @onClick="handleRadio" :value="{text:'吃饭', id:2}" :defaultChecked="true" :disabled="true" className="mRight10"></base-radio>
      <base-radio text="打游戏" @onClick="handleRadio" :value="{text:'打游戏', id:3}" :checked="true" :disabled="false" className="mRight10"></base-radio>
    </div>
    <div style="margin-top:40px;">
      <p style="margin-bottom:20px;">Switch</p>
      <base-switch></base-switch>
    </div>
    <!-- <base-loading :isLoading="isLoading"></base-loading> -->
    <!-- <base-icon type="ceshi"></base-icon> -->
  </div>
</template>

<script>
import BaseButton from './components/BaseButton';
// import BaseLoading from './components/BaseLoading';
// import BaseIcon from './components/BaseIcon';
import BaseCheckbox from './components/BaseCheckbox';
import BaseRadio from './components/BaseRadio';
import BaseSwitch from './components/BaseSwitch';
export default {
  name: 'app',
  data() {
    return {
      isLoading: true
    };
  },
  components: {
    BaseButton,
    // BaseLoading,
    // BaseIcon
    BaseCheckbox,
    BaseRadio,
    BaseSwitch
  },
  methods: {
    handleClick(e) {
      console.log(e);
    },
    handleCheckbox(e, value) {
      console.log(value);
    },
    handleRadio(e, value) {
      console.log(value);
    }
  }
};
</script>

<style lang="less">
@import './style/reset.less';
@import './style/iconfont.css';
@import './style/main.less';
@import './style/utils.css';
#app {
  margin: 10px;
}
</style>
