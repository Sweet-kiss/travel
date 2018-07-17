<template>
  <div class="header">
       <div class="header-left">
           <span class="iconfont">&#xe624;</span>
        </div>
       <div class="header-input">
           <span class="iconfont">&#xe632;</span>
           输入城市/景点/游玩主题
        </div>
      <router-link to='/city'>
         <div class="header-right">
           {{this.city}}
           <span class="iconfont arrow-icon">&#xe63b;</span>
          </div>
      </router-link>
  </div>
</template>

<script>
import { mapState, mapGetters } from 'vuex'
  export default {
    name: 'HomeHeader',
    computed: {
      ...mapState(['city']),
      ...mapGetters(['doubleCity'])
    }
  }
</script>

<style lang="stylus" scoped>
@import '~@/assets/varibles.styl'
.header
  display: flex
  height: .86em
  line-height: 0.86rem
  background: $bgColor
  .header-left
    font-size: .3rem
    width: .64rem
    float: left
    text-align: center
    color:  #fff
  .header-input
    flex: 1
    height: 0.64rem
    line-height: .64rem
    margin-top: 0.12rem
    margin-left: 0.2rem
    background: #fff
    font-size: .3rem
    border-radius: 0.1rem
    color: #ccc
    text-indent: 0.1rem
  .header-right
    font-size: .3rem
    min-width: 1.24rem
    padding: 0 0.1rem
    float: right
    text-align: center
    color:  #fff
    .arrow-icon
      font-size: .24rem
</style>