<template>
  <div>
    <city-header></city-header>
    <city-search
      :cities="cities"
    ></city-search>
    <city-list
      :hot="hotCities"
      :cities="cities"
      :letter="letter"
    ></city-list>
    <city-alphabet
      :cities="cities"
      @change="handleLetterChange"
    ></city-alphabet>
  </div>
</template>

<script>
    import axios from 'axios'
    import CityHeader from './components/Header'
    import CityList from './components/List'
    import CityAlphabet from './components/Alphabet'
    import CitySearch from './components/Search'
    export default {
        name: "City",
        components: {
          CityHeader,
          CityList,
          CityAlphabet,
          CitySearch
        },
        data () {
          return {
            cities: {},
            hotCities: [],
            letter: ''
          }
        },
        methods: {
          getCityInfo () {
            axios.get('/api/city.json')
              .then(this.handleGetCityInfoSucc)
          },
          handleGetCityInfoSucc (res) {
            res = res.data
            if (res.ret && res.data){
              const data = res.data
              this.cities = data.cities
              this.hotCities = data.hotCities
            }
          },
          handleLetterChange (letter) {
            this.letter = letter
          }
        },
        mounted () {
          this.getCityInfo()
        }
    }
</script>

<style lang="stylus" scoped>

</style>
