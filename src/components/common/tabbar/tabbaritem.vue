<template>
  <div class="tab-bar-item" @click="itemClick">
    <div v-if="!isActive">
      <slot name="item-icon"></slot>
    </div>
    <div v-else>
      <slot name="item-icon-active"></slot>
    </div>
    <div :style="activeText">
     <slot name="item-text"></slot>
    </div>
    </div>
</template>

<script>
  export default {
    name: 'tabbaritem',
    props:{
      path: String,
      activeTextColor:{
        type:String,
        default:'red'
      }
    },
   
    computed:{
     isActive(){
       return this.$route.path.indexOf(this.path) !== -1
     },
     activeText(){
       return this.isActive ? {color:this.activeTextColor} : {}
     }
    },
    methods:{
      itemClick(){
        this.$router.currentRoute.path == this.path || this.$router.replace(this.path)
      }
    }
  }
</script>

<style>
  .tab-bar-item{
    flex: 1;
    text-align: center;
    height: 49px;
    font-size: 0.875rem;
  }
  .tab-bar-item img{
    height: 24px;
    width: 1.5rem;
    margin-top: 0.1875rem;
    vertical-align: middle;
    margin-bottom: 0.125rem;
  }
  .active{
    color: red;
  }
</style>
