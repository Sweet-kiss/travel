<template>
  <div id="city">
    <city-header></city-header>
    <city-search></city-search>
    <city-list></city-list>
    <city-alphabet></city-alphabet>
  </div>
</template>

<script>
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
  }
}
</script>

<style lang="stylus" scoped>

</style>
