<template>
  <div class="cityHeader">
     <router-link to="/">
          <div class="iconfont header-back">&#xe624;</div>
     </router-link>
     城市选择
  </div>
</template>

<script>
export default {
  name: 'cityHeader'
}
</script>

<style lang="stylus" scoped>
@import '~@/assets/varibles.styl'
  .cityHeader
    position: relative;
    overflow: hidden
    font-size:0.3rem
    height: 0.86rem
    line-height: 0.86rem
    color:#fff
    background: $bgColor
    text-align: center
    .header-back
      position: absolute
      left: 0
      top: 0
      width: 0.64rem
      text-align: center
      color: #fff
      font-size: 0.35rem
</style>
