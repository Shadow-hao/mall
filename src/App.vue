<template>
  <div id="app">
    <div id="nav">
      <router-view></router-view>
      <tab></tab>
    </div>
  </div>
</template>
<script>
  import tab from 'components/content/tabbar/tab.vue'
  export default {
    name:'app',
    components:{
      tab,
    }
  }
</script>
<style lang="stylus">
@import "assets/css/base.css"
</style>
