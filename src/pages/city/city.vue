<template>
  <div id="city">
    <city-header></city-header>
    <city-search :cities="cities"></city-search>
    <city-list :cities="cities" :hotCities="hotCities" :letter="letter"></city-list>
    <city-alphabet :cities="cities" @change="handleLetterChange"></city-alphabet>
  </div>
</template>

<script>
import axios from 'axios'
import CityHeader from '@/pages/city/components/cityHeader'
import CitySearch from '@/pages/city/components/Search'
import CityList from '@/pages/city/components/list'
import CityAlphabet from '@/pages/city/components/Alphabet'

export default {
  name: 'city',
  components: {
  	CityHeader,
  	CitySearch,
  	CityList,
  	CityAlphabet
  },
  data () {
    return {
    	cities: {},
    	hotCities: [],
    	letter: ''
    }
  },
  methods: {
    getCityInfo(){
    	axios.get('/api/city.json').then(this.handleGetCityInfoSucc)
    },
    handleGetCityInfoSucc (res) {
    	res = res.data
    	if(res.ret && res.data) {
    		const data = res.data
    		this.cities = data.cities
    		this.hotCities = data.hotCities
    	}
    },
    handleLetterChange (letter) {
       this.letter =  letter
       console.log(letter)
    }
  },
  mounted () {
  	this.getCityInfo()
  }
}
</script>

<style lang="stylus" scoped>

</style>
