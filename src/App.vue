<template>
  <div id="app">
    <base-button>button</base-button>
  </div>
</template>

<script>
import BaseButton from './components/BaseButton';
export default {
  name: 'app',
  components: {
    BaseButton
  }
};
</script>

<style lang="less">
@import './style/reset.less';
</style>
