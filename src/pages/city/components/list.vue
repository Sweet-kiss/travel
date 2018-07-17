<template>
  <div class="list" ref="wrapper">
        <div>
            <div class="area">
                 <div class="title border-topbottom">当前城市</div>
                 <div class="button-list">
                    <div class="button-wrapper">
                       <div class="button">{{this.currentCity}}</div>
                    </div>
                 </div>
            </div>
            <div class="area">
                 <div class="title border-topbottom">热门城市</div>
                 <div class="button-list">
                    <div 
                       class="button-wrapper" 
                       v-for="item in hotCities" 
                       :key="item.id" 
                       @click="handleCityClick(item.name)"
                       >
                       <div class="button">{{item.name}}</div>
                    </div>
                 </div>
            </div>
            <div class="area" 
               v-for="(item, key) in cities" 
               :key="key"
               :ref="key"
               >
                 <div class="title border-topbottom">{{key}}</div>
                 <div class="item-list">
                     <div 
                        class="item" 
                        v-for="innerItem in item" 
                        :key="innerItem.id"
                        @click="handleCityClick(innerItem.name)"
                        >{{innerItem.name}}</div>
                 </div>        
            </div>
        </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
import { mapState, mapMutations } from 'vuex'
export default {
  name: 'cityList',
  props: {
     cities: Object,
     hotCities: Array,
     letter: String
  },
  computed: {
    ...mapState({
        currentCity: 'city'
    })
  },
  methods: {
    handleCityClick(city) {
        this.changeCity(city)
        this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper) 
  },
  watch: {
     letter () {
        if(this.letter) {
             console.log(this.letter)
             const element = this.$refs[this.letter][0]
             console.log(element)
            this.scroll.scrollToElement(element)
        }
     }
  
  }
}
</script>

<style lang="stylus" scoped>
.list
  position:absolute
  top:1.7rem
  left:0
  right:0
  bottom: 0
  overflow: hidden
  .title
    line-height:0.5rem
    background: #eee
    padding-left: 0.2rem
    color: #666
    font-size: 0.3rem
  .button-list
    padding 0.1rem 0.6rem 0.1rem 0.1rem
    overflow: hidden
    .button-wrapper
      float: left
      width: 33.33%
      .button
        margin: 0.1rem
        font-size: 0.35rem
        padding: 0.1rem 0;
        text-align: center
        border: 0.02rem solid #ccc
        border-radius: 0.06rem
   .item-list
     .item 
       line-height:0.76rem
       font-size: 0.35rem
       color: #666
       padding-left: 0.2rem
       &:before
         border-color: #ccc
       &:after
         border-color: #ccc    
</style>
