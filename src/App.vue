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
      <base-switch :value="value" :FId="FId" :index="index" class="vswitch" :handle="true" @changeSwitch="changeSwitch"></base-switch>
      <base-switch :value="value" :FId="FId" :index="index" class="vswitch" :handle="true" @changeSwitch="changeSwitch"></base-switch>
    </div>
    <div style="margin-top:40px;">
      <p style="margin-bottom:20px;">Input组件</p>
      <base-input :text="'创业项目名称'" v-model="projectN" placeholder="测试"></base-input>
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
import BaseInput from './components/BaseInput';
export default {
  name: 'app',
  data() {
    return {
      isLoading: true,
      value: false,
      FId: '123',
      index: 0,
      projectN: ''
    };
  },
  components: {
    BaseButton,
    // BaseLoading,
    // BaseIcon
    BaseCheckbox,
    BaseRadio,
    BaseSwitch,
    BaseInput
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
    },
    handleSwitch(e, value) {
      console.log(value);
    },
    changeSwitch(checked, id, index) {
      this.value = !this.value;
      console.log(this.value);
      console.log(index);
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
