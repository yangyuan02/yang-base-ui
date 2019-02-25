<template>
  <div id="app">
    <base-button @handleClick="handleClick">button</base-button>
  </div>
</template>

<script>
import BaseButton from './components/BaseButton';
export default {
  name: 'app',
  components: {
    BaseButton
  },
  methods: {
    handleClick() {
      console.log(22);
    }
  }
};
</script>

<style lang="less">
@import './style/reset.less';
</style>
