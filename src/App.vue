<template>
  <div id="app">
    <!-- <base-button @handleClick="handleClick">button</base-button> -->
    <base-loading :isLoading="isLoading"></base-loading>
    <base-icon type="ceshi"></base-icon>
  </div>
</template>

<script>
// import BaseButton from './components/BaseButton';
import BaseLoading from './components/BaseLoading';
import BaseIcon from './components/BaseIcon';
export default {
  name: 'app',
  data() {
    return {
      isLoading: true
    };
  },
  components: {
    // BaseButton,
    BaseLoading,
    BaseIcon
  },
  methods: {
    handleClick() {
      this.isLoading = false;
    }
  }
};
</script>

<style lang="less">
@import './style/reset.less';
</style>
