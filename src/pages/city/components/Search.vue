<template>
  <div>
     <div class="search">
          <input v-model="keyword" class="search_input" type="text" placeholder="输入城市名或拼音">
         
     </div>
      <div class="search-content">
         <ul>
         	<li class="search-item" v-for="item in list">{{item.name}}</li>
         </ul>
      </div>
 </div>
</template>

<script>
export default {
  name: 'search',
  props: {
  	cities: Object
  },
  data () {
  	return {
  		keyword: '',
  		list: [],
  		timer: null
  	}
  },
  watch: {
  	 keyword () {
        if(this.timer){
        	clearTimeout(this.timer)
        }
        this.timer = setTimeout(()=>{
        	const result = []
        	for(let i in this.cities) {
        		this.cities[i].forEach((value)=>{
                   if(value.spell.indexOf(this.keyword)>-1 || value.name.indexOf(this.keyword)>-1){
                       result.push(value)
                   }
        		})
        	}
        	this.list = result

        },100)
  	 }
  }
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
	.search-content
	   z-index: 1
	   overflow: hidden
	   position: absolute
	   top: 1.68rem
	   left: 0
	   right: 0
	   bottom: 0
	   background: yellow
</style>

