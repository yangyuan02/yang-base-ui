
<template>
  <base-radio text="电影" @onClick="handleRadio" :value="{text:'电影', id:1}" className="mRight10">
  </base-radio>
</template>
<script>
import BaseRadio from './BaseRadio';
export default {
  components: {
    BaseRadio
  }
};
</script>

<style lang="less" scoped>
</style>