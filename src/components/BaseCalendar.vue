<template>
  <div>

  </div>
</template>
<script>
export default {
  data() {
    return {
      weekTable: [
        // 日历头
        {
          cn: ['星期日', '星期一', '星期二', '星期三', '星期四', '星期五', '星期六'],
          cns: ['日', '一', '二', '三', '四', '五', '六'],
          en: ['Sun', 'Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat']
        },
        {
          cn: ['星期一', '星期二', '星期三', '星期四', '星期五', '星期六', '星期日'],
          cns: ['一', '二', '三', '四', '五', '六', '日'],
          en: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
        }
      ]
    };
  },
  computed: {
    getMonthDays: (year, month) => new Date(year, month), // 获取当月天数
    getWeekDay: (year, month, day) => new Date(year, month, day).getDate() + 1, // 获取星期几
    getWeeksInMonth: (yaer, month) => {
      // 获取月份有几个星期
      const days = this.getMonthDays(yaer, month);
      const firstDayWeekDay = this.getWeekDay(yaer, month, 1);
      return Math.ceil(days + firstDayWeekDay);
    }
  }
};
</script>