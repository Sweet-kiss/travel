<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
	    <!-- slides -->
	     <swiper-slide v-for="item in swiperList"><img class="swiper-img" :src="item.imgUrl" alt=""></swiper-slide>
	  
	    <!-- Optional controls -->
	    <div class="swiper-pagination"  slot="pagination"></div>
   </swiper>
  </div>

</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
  	 return {
  	 	swiperOption: {
  	 		pagination: '.swiper-pagination',
  	 		loop: true
  	 	},
  	 	swiperList: [
	  	 	{
               id: '0001',
               imgUrl: 'https://s.qunarzz.com/bnb_hy2/images/home/banner/football.jpg'
	  	 	},
	  	 	{
               id: '0002',
               imgUrl: 'https://s.qunarzz.com/bnb_hy2/images/home/banner/haibianlang.jpg' 	  	 		
	  	 	},
	  	 	{
               id: '0003',
               imgUrl: 'https://img1.qunarzz.com/desmisact/images/1805/14/3cc0369fb8b5a.jpg' 	  	 		
	  	 	}
  	 	]
  	 }
  }
}
</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
  background: #fff !important
.wrapper
  overflow: hidden
  width:100%
  height: 0
  padding-bottom: 50%
  .swiper-img
     width: 100%;
     background: #ccc
</style>
