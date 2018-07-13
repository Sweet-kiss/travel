<template>
  <ul class="list">
      <li class="item">A</li>
      <li class="item">A</li>
      <li class="item">A</li>
      <li class="item">A</li>
      <li class="item">A</li>
      <li class="item">A</li>      
  </ul>
</template>

<script>
export default {
  name: 'cityList'
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/varibles.styl'
  .list
    display: flex
    flex-direction: column
    justify-content: center
    position: absolute
    top: 1.58rem
    right: 0
    bottom: 0
    width: 0.4rem
    .item
      line-height: 0.44rem
      text-align:center
      list-style: none;
      font-size: 0.4rem
      color: #00bcd4
</style>
