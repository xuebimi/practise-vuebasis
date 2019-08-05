<template>
    <div>
      <img :src="imgSrc"  :height = 'bgHeight' :width = 'bgWidth'
           style="z-index: -1;position: absolute;top:0;left: 0;right: 0;bottom: 0;margin: auto;"/>
      <div style="border: 1px solid #9ac2ff;width:300px;height:200px;
      position: absolute;top: 0;bottom: 0;left: 0;right: 0;margin: auto;border-radius: 5px">
        <h1 style="color: #9ac2ff">登录页</h1>
        <el-button type="primary" @click="funcHome()">点击进入</el-button>
      </div>
    </div>
</template>

<script>
export default {
  name: 'login',
  data () {
    return {
      bgHeight: '',
      bgWidth: '',
      imgSrc: '../../static/images/bg2.jpg',
      flag: 0
    }
  },
  methods: {
    funcHome () {
      this.$router.push({path: '/home'})
    }
  },
  mounted () {
    this.bgHeight = `${document.documentElement.clientHeight}` + 'px'
    this.bgWidth = `${document.documentElement.clientWidth}` + 'px'
  }
}
</script>

<style scoped>

</style>
