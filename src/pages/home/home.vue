<template>
  <div>
       <home-header></home-header>
       <home-swiper :list="swiperList"></home-swiper>
       <home-icons :icons="iconsList"></home-icons>
       <home-recommend :recommend="recommendList"></home-recommend>
       <home-week :week="weekendList"></home-week>
   </div>
</template>

<script>
import axios from 'axios'
import HomeHeader from './components/header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/icons'
import HomeRecommend from './components/Recommend'
import HomeWeek from './components/week'
import { mapState } from 'vuex'
  export default {
    name: 'Home',
    components: {
    	HomeHeader,
    	HomeSwiper,
    	HomeIcons,
      HomeRecommend,
      HomeWeek
    },
    data () {
      return {
        lastCity: '',
        swiperList: [],
        iconsList: [],
        recommendList: [],
        weekendList: []
      }
    },
    computed: {
      ...mapState(['city'])
    },
    methods: {
        getHomeInfo () {
           axios.get('/api/index.json?city='+this.city).then(this.getHomeInfoSucc)
        },
        getHomeInfoSucc (res) {
            res = res.data
            if (res.ret && res.data) {
              this.swiperList = res.data.swiperList
              this.iconsList = res.data.iconList
              this.recommendList = res.data.recommendList
              this.weekendList = res.data.weekendList
              console.log(this.weekendList)
            }
            console.log(res)
        }
    },
    mounted () {
      this.lastCity = this.city
      this.getHomeInfo()
    },
    activated () {
       if(this.lastCity !== this.city) {
          this.lastCity = this.city
          this.getHomeInfo()
       }
    }
  }
</script>

<style>
</style>