<template>
  <div class="searchBox">
    <div class="searchItem" v-for="(item, index) in conditions" :key="index">
      <base-input v-if="item.type === 'String'" />
      <base-select v-if="item.type === 'Select'" />
    </div>
  </div>
</template>

<script>
import BaseInput from './BaseInput';
import BaseSelect from './BaseSelect';
export default {
  components: {
    BaseInput,
    BaseSelect
  },
  props: {
    conditions: {
      // searchBox表单类型
      type: Array,
      default: () => []
    }
  }
};
</script>
