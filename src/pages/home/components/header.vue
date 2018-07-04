<template>
  <div class="header">
       <div class="header-left">
           <span class="iconfont">&#xe624;</span>
        </div>
       <div class="header-input">
           <span class="iconfont">&#xe632;</span>
           输入城市/景点/游玩主题
        </div>
       <div class="header-right">
         城市
         <span class="iconfont arrow-icon">&#xe63b;</span>
        </div>
  </div>
</template>

<script>
  export default {
    name: 'HomeHeader'
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
    width: 1.24rem
    float: right
    text-align: center
    color:  #fff
    .arrow-icon
      font-size: .24rem
</style>