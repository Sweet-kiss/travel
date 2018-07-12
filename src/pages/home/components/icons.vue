<template>
   <div  class="icons">
      <swiper :options="swiperOption">
         <swiper-slide v-for="(page, index) in pages" :key="index">
            <div class="icon" v-for="item in page" :key="item.id">
                <div class="icon-img">
                   <img class="icon-img-content" :src="item.imgUrl" alt="">
                </div>
                <p class="icon-desc">{{item.desc}}</p>
            </div>
         </swiper-slide>
  
     </swiper>
 
            
   </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
     icons: Array
  },
  data () {
    return {
       swiperOption: {
        autoplay: false
       }
     }
  },
  computed: {
    pages () {
      const pages = []
      this.icons.forEach((item, index) => {
         const page = Math.floor(index/8)
         if(!pages[page]) {
            pages[page] = []
         }
         pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~@/assets/varibles.styl'
.icons >>> .swiper-container
    height: 0
    padding-bottom: 50%
.icons
  margin-top: 0.1rem
  .icon
    position: relative
    overflow: hidden
    float:left
    width:25%
    padding-bottom:25%
    .icon-img
      position: absolute
      top: 0
      left: 0
      right: 0
      bottom: .3rem
      box-sizing: border-box
      padding: 0.1rem
      .icon-img-content
        display: block
        height: 100%
        margin: 0 auto
    .icon-desc
      position: absolute
      left: 0
      right: 0
      bottom: 0
      text-align: center
      font-size: .3rem
      color: #333
      height: 0.44rem
	    line-height: 0.44rem
 </style>
