<template>
   <div class="icons">
    <div class="icon">
        <div class="icon-img">
           <img class="icon-img-content" src="http://pic.c-ctrip.com/h5/group_travel/icon610-index_15.png" alt="">
        </div>
        <p class="icon-desc">热门景点</p>
    </div>

    <div class="icon">
        <div class="icon-img">
           <img class="icon-img-content" src="http://pic.c-ctrip.com/h5/group_travel/icon610-index_15.png" alt="">
        </div>
        <p class="icon-desc">热门景点</p>
    </div>

    <div class="icon">
        <div class="icon-img">
           <img class="icon-img-content" src="http://pic.c-ctrip.com/h5/group_travel/icon610-index_15.png" alt="">
        </div>
        <p class="icon-desc">热门景点</p>
    </div>

    <div class="icon">
        <div class="icon-img">
           <img class="icon-img-content" src="http://pic.c-ctrip.com/h5/group_travel/icon610-index_15.png" alt="">
        </div>
        <p class="icon-desc">热门景点</p>
    </div>

    <div class="icon">
        <div class="icon-img">
           <img class="icon-img-content" src="http://pic.c-ctrip.com/h5/group_travel/icon610-index_15.png" alt="">
        </div>
        <p class="icon-desc">热门景点</p>
    </div>

    <div class="icon">
        <div class="icon-img">
           <img class="icon-img-content" src="http://pic.c-ctrip.com/h5/group_travel/icon610-index_15.png" alt="">
        </div>
        <p class="icon-desc">热门景点</p>
    </div>
    <div class="icon">
        <div class="icon-img">
           <img class="icon-img-content" src="http://pic.c-ctrip.com/h5/group_travel/icon610-index_15.png" alt="">
        </div>
        <p class="icon-desc">热门景点</p>
    </div>

    <div class="icon">
        <div class="icon-img">
           <img class="icon-img-content" src="http://pic.c-ctrip.com/h5/group_travel/icon610-index_15.png" alt="">
        </div>
        <p class="icon-desc">热门景点</p>
    </div>                
   </div>
</template>

<script>
export default {
  name: 'HomeIcons'
}
</script>

<style lang="stylus" scoped>
@import '~@/assets/varibles.styl'
.icons
  overflow: hidden
  height: 0;
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
