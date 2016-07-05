<style lang=less>
</style>

<template>
  <span>{{getLen(new Date(this.the_time))}}</span>
</template>

<script>
  // import store from '../store'
  export default {
    props: {
      the_time: {
        type: Number,
        required: true,
        default: new Date().getTime()
      }
    },
    components: {
    },
    data: function () {
      return {
      }
    },
    ready () {
    },
    methods: {
      getLen: function (that_time) {
        var day, desc, hour, interval, minute, month, now, second, year
        second = 1000
        minute = second * 60
        hour = minute * 60
        day = hour * 24
        month = day * 30
        year = month * 12
        now = Date.now()
        interval = now - that_time
        if (interval < minute) {
          desc = parseInt(interval / second, 10) + '秒前'
        } else if (interval < hour) {
          desc = parseInt(interval / minute, 10) + '分钟前'
        } else if (interval < day) {
          desc = parseInt(interval / hour, 10) + '小时前'
        } else if (interval < month) {
          desc = parseInt(interval / day, 10) + '天前'
        } else if (interval < year) {
          desc = parseInt(interval / month, 10) + '个月前'
        } else {
          desc = parseInt(interval / year, 10) + '年前'
        }
        return desc
      }
    }
  }
</script>
