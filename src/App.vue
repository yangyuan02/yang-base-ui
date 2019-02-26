<template>
  <div id="app">
    <div>
      <p>Button按钮</p>
      <base-button @onClick="handleClick" text="默认按钮" className="mgL10" icon="shezhi"></base-button>
      <base-button @onClick="handleClick" text="主要按钮" :disabled="true" type="primary" className="mgL10"></base-button>
      <base-button @onClick="handleClick" text="成功按钮" :disabled="true" type="success" className="mgL10"></base-button>
      <base-button @onClick="handleClick" text="警告按钮" :disabled="true" type="warning" className="mgL10"></base-button>
    </div>
    <!-- <base-loading :isLoading="isLoading"></base-loading> -->
    <!-- <base-icon type="ceshi"></base-icon> -->
    <!-- <base-checkbox text="电影"></base-checkbox> -->
  </div>
</template>

<script>
import BaseButton from './components/BaseButton';
// import BaseLoading from './components/BaseLoading';
// import BaseIcon from './components/BaseIcon';
// import BaseCheckbox from './components/BaseCheckbox';

export default {
  name: 'app',
  data() {
    return {
      isLoading: true
    };
  },
  components: {
    BaseButton
    // BaseLoading,
    // BaseIcon
    // BaseCheckbox
  },
  methods: {
    handleClick(e) {
      console.log(e);
    }
  }
};
</script>

<style lang="less">
@import './style/reset.less';
@import './style/main.less';
@import './style/iconfont.css';
#app {
  margin: 10px;
}
.mgL10 {
  margin-right: 10px;
}
</style>
