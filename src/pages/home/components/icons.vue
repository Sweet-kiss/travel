<template>
   <div class="icons">
      <swiper>
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
  data () {
    return {
      iconList: [
         {
            id: '0001',
            imgUrl: 'https://pic2.itrip.com/p/20180705101108-509.png',
            desc: '景点门票'
         },
         {
            id: '0002',
            imgUrl: 'https://pic2.itrip.com/p/20180705101114-614.png',
            desc: '滑雪季'          
         },
         {
            id: '0003',
            imgUrl: 'https://pic2.itrip.com/p/20180705100605-652.png',
            desc: '泡温泉'          
         },
         {
            id: '0004',
            imgUrl: 'https://pic2.itrip.com/p/20180705100612-60.png',
            desc: '动植物园'          
         },
         {
            id: '0005',
            imgUrl: 'https://pic2.itrip.com/p/20180705100618-154.png',
            desc: '滑雪季'          
         },
         {
            id: '0006',
            imgUrl: 'https://pic2.itrip.com/p/20180705100624-473.png',
            desc: '滑雪季'          
         },
         {
            id: '0007',
            imgUrl: 'https://pic2.itrip.com/p/20180705100630-911.png',
            desc: '滑雪季'          
         },
         {
            id: '0008',
            imgUrl: 'https://pic2.itrip.com/p/20180705100637-801.png',
            desc: '滑雪季'          
         },
         {
            id: '0009',
            imgUrl: 'https://pic2.itrip.com/p/20180705100637-801.png',
            desc: '滑雪季'          
         },
         {
            id: '0010',
            imgUrl: 'https://pic2.itrip.com/p/20180705100637-801.png',
            desc: '滑雪季'          
         }
      ]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
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
      bottom: .44rem
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
