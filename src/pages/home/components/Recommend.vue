<template>
  <div>
     <div class="recommend-title">热销推荐</div>
     <ul>
       <li class="item border-bottom" v-for="item in recommend" :key="item.id">
        
            <img class="item-img" :src="item.imgUrl" alt="">
         
            <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-desc">{{item.desc}}</p>
            <button class="item-button">查看详情</button>
         </div>
         
       </li>
     </ul>
  </div>
</template>

<script>
export default {
  name: 'recommen',
  props: {
     recommend: Array
  },
  data () {
     return {
    }
  }
}
</script>

<style lang="stylus" scoped>
  .recommend-title
    margin-top: 0.2rem
    line-height: 0.8rem
    background: #eee
    font-size: 0.3rem
    text-indent: 0.2rem
  .item
    overflow: hidden
    display: flex
    height: 1.9rem
    .item-img
      width: 1.7rem
      height: 1.7rem
      padding: 0.1rem
    .item-info
      position: relative
      flex:1
      padding: 0.1rem
      .item-title
        line-height: 0.54rem
        font-size: 0.32rem
      .item-desc
        line-height: 0.4rem
        font-size: 0.25rem
        color: #ccc
      .item-button
        position: absolute;
        left: 0.1rem
        bottom: 0.2rem
        background: #ff9300
        padding: 0.1rem 0.2rem;
        border-radius: 0.06rem;
        font-size:0.15rem
        border:none
        color:#fff
</style>
