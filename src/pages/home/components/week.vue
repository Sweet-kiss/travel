<template>
   <div>
      <div class="homeWeek-title">周末去哪儿</div>
      <div class="spot_wrapper">
        <div class="spot_list" v-for="item in week">
          <a class="lin_j" href="#">
               <img class="spot_img" :src="item.imgUrl" alt="">
               <p class="spot_name">{{item.title}}</p>
               <p class="spot_text">{{item.desc}}</p>
          </a>
        </div>
      </div>
       
   </div>
  
</template>

<script>
export default {
  name: 'HomeWeek',
  props:{
     week: Array
  },
  data () {
    return {
    }
  }
}
</script>

<style lang="stylus" scoped>
  .homeWeek-title
    margin-top: 0.2rem
    line-height: 0.8rem
    background: #eee
    font-size: 0.3rem
    text-indent: 0.2rem
  .spot_list
    width: 100%
    overflow: hidden
    .lin_j
      display: block
      width: 100%
      .spot_img
        width: 100%
      .spot_name
        font-size: 0.35rem
        color: #121111
        margin-top: 0.2rem
        margin-bottom: 0.15rem
        text-indent: 0.2rem
      .spot_text
        font-size: 0.2rem
        color: #373635
        margin-bottom: 0.4rem
        text-indent: 0.2rem
</style>
