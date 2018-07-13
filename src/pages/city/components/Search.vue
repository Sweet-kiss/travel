<template>
  
     <div class="search">
          <input class="search_input" type="text" placeholder="输入城市名或拼音">
     </div>
  
</template>

<script>
export default {
  name: 'search'
}
</script>

<style lang="stylus" scoped>
	@import '~@/assets/varibles.styl'
	.search
	   width: 100%
	   font-size: 0
	   padding: 0.1rem 0;
	   background: $bgColor
	   text-align: center
	   overflow:hidden
	   .search_input
	     box-sizing: border-box
	     width: 95%
	     border: none
	     height:0.62rem
	     line-height:0.62rem
	     padding:0 0.1rem
	     text-align: center
	     border-radius: 0.06rem
</style>

