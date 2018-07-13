<template>
  <ul class="list">
      <li class="item" v-for="(item, key) in cities" :key="key">{{key}}</li>      
  </ul>
</template>

<script>
export default {
  name: 'cityList',
  props: {
    cities: Object
  }
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
      line-height: 0.48rem
      text-align:center
      list-style: none;
      font-size: 0.35rem
      color: #00bcd4
</style>
