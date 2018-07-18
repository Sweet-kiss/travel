<template>
  <div class="cityDetail">
      <city-banner></city-banner>
      <detail-header></detail-header>
      <div class="content"></div>
  </div>
</template>

<script>
import CityBanner from './components/Banner'
import DetailHeader from './components/header'
export default {
  name: 'cityDetail',
  components: {
  	CityBanner,
  	DetailHeader
  }
}
</script>

<style lang="stylus" scoped>
 .content
   height: 50rem
</style>
