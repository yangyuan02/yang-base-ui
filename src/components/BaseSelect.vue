<template>
  <div class="select">
    <div class="inner">
      <div class="inputWrapper" @click.stop="show = !show">
        <input type="text" readonly placeholder="请选择" :value="value" />
        <span class="清除"></span>
      </div>
      <ul class="options" v-show="show">
        <li v-for="(item, index) in options" :key="index" @click.stop="choose(item.value)">{{item.value}}</li>
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
    },
    value: {
      // 输入框显示值
      type: String,
      default: ''
    }
  },
  data() {
    return {
      show: false,
      options: [{ value: '西红柿炒鸡蛋' }, { value: '青椒炒鸡蛋' }, { value: '回锅肉' }]
    };
  },
  mounted() {
    document.addEventListener(
      'click',
      () => {
        this.show = false;
      },
      false
    );
  }
};
</script>