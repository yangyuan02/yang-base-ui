<template>
  <div id="app">
    <!-- <base-button @handleClick="handleClick">button</base-button> -->
    <base-loading :isLoading="isLoading"></base-loading>
  </div>
</template>

<script>
// import BaseButton from './components/BaseButton';
import BaseLoading from './components/BaseLoading';
export default {
  name: 'app',
  data() {
    return {
      isLoading: true
    };
  },
  components: {
    // BaseButton,
    BaseLoading
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
