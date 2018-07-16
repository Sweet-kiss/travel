<template>
  <ul class="list">
      <li 
      class="item" 
      v-for="item in letters" 
      :ref="item"
      :key="item" 
      @touchstart="handleTouchStart"
      @touchMove="handleTouchMove"
      @touchEnd="handleTouchEnd"
      @click="handleLetterClick"
      >
        {{item}}
      </li>      
  </ul>
</template>

<script>
export default {
  name: 'cityList',
  props: {
    cities: Object
  },
  data () {
    return {
        touchStatus: false
    }
  },
  methods: {
     handleLetterClick (e) {
        this.$emit('change', e.target.innerText)
     },
     handleTouchStart () {
        this.touchStatus = true
     },
     handleTouchMove () {
        if (this.touchStatus) {
           const startY = this.$refs['A'][0].offsetTop
           console.log(startY)
           console.log('1')
        }
     },
     handleTouchEnd () {
        this.touchStatus = false
     }
  },
  computed: {
    letters () {
       const letters = []
       for (let i in this.cities) {
          letters.push(i)
       }
       return letters
    }
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
