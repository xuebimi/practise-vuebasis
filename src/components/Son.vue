<template>
  <div style="border: 1px solid salmon;">
    <h2>子组件</h2>
    <div>子听到父说：{{msg}}</div>
    <el-input v-model="sonMsg" placeholder="向父亲说点什么..." style="width: 200px"></el-input><el-button type="plain" @click="funcSend()">发送给父亲</el-button>
  </div>
</template>

<script>
export default {
  name: 'son',
  props: ['msg'],
  data () {
    return {
      sonMsg: ''
    }
  },
  methods: {
    funcSend () {
      this.$emit("sendMsg", this.sonMsg)
    }
  }
}
</script>

<style scoped>

</style>
