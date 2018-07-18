<template>
<div>
    <div class="cityBanner" @click="handleBannerClick">
       <img class="banner-img" src="http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg" alt="">
       <div class="banner-info">
          <div class="banner-title">故宫(AAAAA景区)</div>
          <div class="banner-number"><span class="iconfont arrow-icon">&#xe67f;</span>39</div>
       </div>
    </div>
    <common-gallary 
      :imgs="imgs" 
      v-show="showGallary"
      @close="handleGallaryClose"
    ></common-gallary>
</div>
</template>

<script>
import CommonGallary from '@/common/gallary/Gallary'
export default {
  name: 'cityBanner',
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/201403/10/6a18aabe4e02e211552c25da2c8d6c93.jpg_r_800x800_dc604303.jpg',
      'http://img1.qunarzz.com/sight/p0/1711/e6/e6c63a841145702a3.img.jpg_r_800x800_e3d697bd.jpg'
    ]
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  },
  components: {
    CommonGallary
  }
}
</script>

<style lang="stylus" scoped>
 .cityBanner
   position: relative
   overflow: hidden
   height: 0
   padding-bottom: 55%
   .banner-img
     width: 100%
   .banner-info
     display:  flex
     font-size: 0.32rem
     position: absolute
     left: 0
     right: 0
     bottom: 0
     color: #fff
     line-height: 0.6rem
     background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
     .banner-title
       flex: 1
       padding:0 0.2rem
     .banner-number
       margin-top: 0.14rem
       padding: 0 0.4rem
       height: 0.32rem
       line-height: 0.32rem
       border-radius: 0.2rem
       background: rgba(0, 0, 0, 0.8)
       font-size: 0.24rem
</style>
