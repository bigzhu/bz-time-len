<template>
  <span>{{timeLen(new Date(this.the_time), lang)}}</span>
</template>

<script>
  import timeLen from 'bz-lib/functions/timeLen'
  export default {
    props: {
      the_time: {
        type: Number,
        required: true,
        default: new Date().getTime()
      },
      lang: {
        type: String,
        default: 'cn'
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
      timeLen: timeLen
    }
  }
</script>
