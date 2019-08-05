<template>
  <div>
    <i class="el-icon-switch-button" style="position: fixed;top: 20px;right: 20px;font-size: 24px;color: white;cursor:pointer;" @click="funcLogout"></i>
    <img :height='homeHeight' :width="homeWidth" style="background-image: linear-gradient(-225deg, #2CD8D5 0%, #C5C1FF 56%, #FFBAC3 100%);
    position: absolute;left: 0;right: 0;top: 0;bottom: 0;margin: auto;z-index: -1;">
    <div>
      <h1 style="color: white">
        主页(父组件)
      </h1>
      <el-input v-model="fatherMsg" style="width: 200px" placeholder="给儿子说点什么..."></el-input>
      <div>父听到子说:{{sonMsg}}</div>
      <son :msg="fatherMsg" @sendMsg="showSonMsg"></son>
    </div>
  </div>
</template>

<script>
import Son from '@/components/Son'
export default {
  name: 'home',
  components: {Son},
  data () {
    return {
      homeHeight: '',
      homeWidth: '',
      sonMsg: '',
      fatherMsg: ''
    }
  },
  methods: {
    showSonMsg(msg) {
      this.sonMsg = msg
    },
    funcLogout () {
      this.$router.push({path: '/'})
    }
  },
  mounted () {
    this.homeHeight = `${document.documentElement.clientHeight}` + 'px'
    this.homeWidth = `${document.documentElement.clientWidth}` + 'px'
  }
}
</script>

<style scoped>

</style>
