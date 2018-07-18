<template>
  <div class="DetailHeader">
     <router-link 
          tag="div" to="/" 
          class="header-abs"
          v-show="showAbs"
          >
        <span class="iconfont">&#xe624;</span>
     </router-link>
     <div 
        class="header-fixed"  
        v-show="!showAbs"
        :style="opacityStyle"
           >
        <router-link 
           tag="div" 
           to="/" 
           class="header-abs header-back"
           ><span class="iconfont">&#xe624;</span></router-link>
        景点详情
     </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
      return {
         showAbs: true,
         opacityStyle: {
            opacity: 0
         }
      }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if(top>60) {
         let opacity = top/140
         opacity = opacity>1?1:opacity
         this.opacityStyle = {
            opacity
         }
         this.showAbs = false
      } else {
         this.showAbs = true
      }
    }
  },
  activated () {
     window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
     window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
@import '~@/assets/varibles.styl'
  .header-abs
    position: absolute
    font-size: 0.32rem
    color:#fff
    left: 0.2rem
    top: 0.2rem
    width: 0.8rem
    height: 0.8rem
    line-height: 0.8rem
    border-radius: 0.4rem
    text-align: center
    background: rgba(0, 0, 0, 0.3)
  .header-fixed
    position: fixed
    top: 0
    left: 0
    right: 0
    overflow: hidden
    font-size:0.3rem
    height: 0.86rem
    line-height: 0.86rem
    color:#fff
    background: $bgColor
    text-align: center
    .header-back
       background: none
       position: absolute
       left: 0.2rem
       top: 0rem
       width: 0.8rem
       height: 0.8rem
</style>
