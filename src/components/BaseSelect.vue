<template>
  <div class="select">
    <div class="inner">
      <div class="inputWrapper">
        <input type="text" readonly placeholder="请选择" />
        <span class="清楚"></span>
      </div>
      <ul class="options">
        <li v-for="(item, index) in options" :key="index">{{item.value}}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    data: {
      // options数据
      type: Array,
      default: () => []
    },
    disabled: {
      // 是否允许点击展开options
    },
    clearFun: {
      // 清空事件
    },
    multiple: {
      // 是否多选
      type: Boolean,
      default: false
    },
    changeFun: {
      //选中改变的事件
    }
  },
  data() {
    return {
      options: [{ value: '西红柿炒鸡蛋' }, { value: '青椒炒鸡蛋' }, { value: '回锅肉' }]
    };
  }
};
</script>